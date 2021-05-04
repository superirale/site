<template>
  <div>
    <Header />
    <div class="container">
      <div class="profile">
      <div class="profile-body">
        <div class="profile-image">
          <img src="../assets/images/usman.jpeg">
        </div>
        <div class="profile-name">
          <h1>Usman Irale</h1>
        </div>
        <div class="profile-description">
          <p>Software Engineer.<br> Working remotly at Telios Support Services</p>
        </div>

        <div class="profile-social-accounts">
          <ul>
            <li><a href=""><i class="fa fa-linkedin"></i></a></li>
            <li><a href=""><i class="fa fa-twitter"></i></a></li>
            <li><a href=""><i class="fa fa-github"></i></a></li>
            <li><a href=""><i class="fa fa-stack-overflow"></i></a></li>
          </ul>
        </div>
      </div>
    </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      isHomepage: true
    }
  },
  head() {
        return {
            bodyAttrs: {
                class: this.isHomepage ? 'bg' : 'bg-white'
            }
        }
    },
}
</script>

<style>

</style>
