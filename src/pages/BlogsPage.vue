<template>
  <div class="blogs-page">
    <div class="col-md-3">
      <ul>
        <li>
          <p></p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlogsPage',
  props: {
    blogs: {
      type: Object,
      required: true
    }
  },
  setup() {
    return {}
  },
  components: {}
}
</script>

<style lang="scss" scoped>

</style>
