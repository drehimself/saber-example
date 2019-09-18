<template>
  <div>
    <Navbar />
    <slot name="default" />
  </div>
</template>

<script>
import Navbar from '../components/Navbar.vue'

export default {
  components: {
    Navbar
  },
  props: ['page'],
  head() {
    const pageTitle = this.page && this.page.title
    return {
      title: pageTitle ?
        `${pageTitle} - ${this.$siteConfig.title}` :
        this.$siteConfig.title
    }
  }
}
</script>

<style>
  #nprogress .bar {
    background: red !important;
  }

  .page-enter-active, .page-leave-active {
    transition: opacity .5s;
  }
  .page-enter, .page-leave-to {
    opacity: 0;
  }

</style>
