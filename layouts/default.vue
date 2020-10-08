<template>
  <div class="app">
    <!--  -->
    <!-- top navigation bar start -->
    <header class="navbar elevate-on-scroll">
      <nuxt-link to="/" tag="div" class="brand">
        <img src="~/assets/images/aura_logo.png" class="logo" alt="aura-logo">
        <span class="app-title">{{ appTitle }}</span>
      </nuxt-link>
      <div class="nav-links right desktop">
        <ul class="nav-links-list">
          <nuxt-link to="/" tag="li" tabindex="0" class="nav-link">
            Home
          </nuxt-link>
          <nuxt-link to="/about" tag="li" tabindex="0" class="nav-link">
            About
          </nuxt-link>
          <nuxt-link to="/capabilities" tag="li" tabindex="0" class="nav-link">
            Capabilities
          </nuxt-link>
          <nuxt-link to="/services" tag="li" tabindex="0" class="nav-link">
            Services
          </nuxt-link>
        </ul>
      </div>
      <div class="cta">
        <nuxt-link to="/contact" tag="button" class="btn pill small">
          Contact Us
        </nuxt-link>
      </div>
      <div class="fa-icon burger btn mobile" tabindex="0" />
    </header>
    <!-- top navigation bar end -->
    <!-- side nav start -->
    <!-- <aside class="side-nav">
      <div class="title">
        <nuxt-link to="/" tag="div" class="brand">
          <img src="~/assets/images/aura_logo.png" class="logo" alt="aura-logo">
          <span class="app-title">{{ appTitle }}</span>
        </nuxt-link>
      </div>
    </aside> -->
    <!-- side nav drawer end -->
    <!--  -->
    <!-- main start -->
    <nuxt />
    <!-- main end -->
    <!--  -->
    <!-- footer start -->
    <footer>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </footer>
    <!-- footer end -->
  </div>
</template>

<script>
export default {
  data () {
    return {
      appTitle: 'Aura'
    }
  }
}
</script>

<style lang="scss">
</style>
