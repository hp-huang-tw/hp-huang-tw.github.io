<template>
  <div class="profile-page">
    <div class="wrapper">
      <div class="page-header page-header-small" filter-color="green">
        <div class="page-header-image" data-parallax="true" :style=coverStyle>
        </div>
        <div class="container">
          <div class="content-center">
            <div class="cc-profile-image">
              <a href="#">
                <img :src="profile.imageUrl" alt="Image"/>
              </a>
            </div>
            <div class="h2 title">{{ profile.name }}</div>
            <p class="category text-white">{{ profile.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Profile',
  props: {
    profile: {
      type: Object,
      default: () => {
        return {
          name: '',
          description: '',
          imageUrl: '',
          coverUrl: ''
        }
      }
    }
  },
  computed: { 
    coverStyle () {
      return { backgroundImage: `url(${this.profile.coverUrl})` }
    }
  }
}
</script>
