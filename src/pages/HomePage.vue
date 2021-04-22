<template>
  <div class="home flex-grow-1 d-flex flex-column align-items-center justify-content-center">
    <img src="https://bcw.blob.core.windows.net/public/img/8600856373152463" alt="CodeWorks Logo">
    <h1 class="my-5 bg-dark text-light p-3 rounded d-flex align-items-center">
      Blogger
    </h1>
    <blogs v-for="blog in state.blogs" />
  </div>
</template>

<script>
import { computed, reactive, onMounted } from 'vue'
import { AppState } from '../AppState'
import { blogsService } from '../services/BlogsService'

export default {
  name: 'Home',
  setup() {
    const state = reactive({
      blogs: computed(() => AppState.blogs)
    })
    onMounted(async() => {
      try {
        await blogsService.getAll()
      } catch (error) {
        Notification.toast('Error: ' + error, 'error')
      }
    })
    return {
      state
    }
  }
}
</script>

<style scoped lang="scss">
.home{
  text-align: center;
  user-select: none;
  > img{
    height: 200px;
    width: 200px;
  }
}
</style>
