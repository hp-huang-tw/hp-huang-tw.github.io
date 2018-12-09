<template>
  <div class="app">
    <navigation></navigation>
    <div class="page-content">
      <div>
        <profile :profile="profile"></profile>
      </div>
    </div>
  </div>
</template>

<script>
import Navigation from '../components/navigation'
import Profile from '../components/profile'
export default {
  name: 'Index',
  components: {
    Navigation,
    Profile
  },
  data () {
    return {
      profile: {
        name: 'Anna Huang',
        description: 'Software Engineer, Web Developer, iOS devepoper',
        imageUrl: 'me.jpg',
        coverUrl: 'bootstrap/images/cc-bg-1.jpg'
      }
    }
  }
}
</script>
