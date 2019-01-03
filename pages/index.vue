<template>
  <a href="javascript:void(0);" @click="redirect">view on linkedin</a>
</template>

<script>
export default {
  name: 'Index',
  methods: {
    redirect() {
      const linkedinUrl = 'https://www.linkedin.com/in/hp-huang/'
      this.$ga.event('outlink', 'click', linkedinUrl)
      window.location.assign(linkedinUrl)
    }
  }
}
</script>
