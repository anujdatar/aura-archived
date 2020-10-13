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
          <nuxt-link
            v-for="(item, i) in routes"
            :key="i"
            :to="item.path"
            tag="li"
            tabindex="0"
            class="nav-link"
          >
            {{ item.title }}
          </nuxt-link>
        </ul>
        <div class="cta">
          <nuxt-link to="/contact" tag="button" class="btn pill small">
            Contact Us
          </nuxt-link>
        </div>
      </div>
      <div class="fa-icon burger btn mobile" tabindex="0" />
    </header>
    <!-- top navigation bar end -->
    <!-- side nav start -->
    <aside class="side-nav mobile">
      <div class="side-nav-links">
        <nuxt-link to="/" tag="div" class="brand">
          <img src="~/assets/images/aura_logo.png" class="logo" alt="aura-logo">
          <span class="app-title">{{ appTitle }}</span>
        </nuxt-link>
        <hr style="color: var(--secondary);width: 100%">
        <div class="nav-links">
          <ul class="nav-links-list">
            <nuxt-link
              v-for="(item, i) in routes"
              :key="i"
              :to="item.path"
              tag="li"
              tabindex="0"
              class="nav-link"
            >
              {{ item.title }}
            </nuxt-link>
          </ul>
          <div class="cta">
            <nuxt-link to="/contact" tag="button" class="btn pill">
              Contact Us
            </nuxt-link>
          </div>
        </div>
      </div>
    </aside>
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
      appTitle: 'Aura',
      routes: [
        { title: 'Home', path: '/' },
        { title: 'About', path: 'about' },
        { title: 'Capabilities', path: 'capabilities' },
        { title: 'Services', path: 'services' }
      ],
      drawer: false
    }
  },
  mounted () {
    // handle scroll event for navigation bar
    window.addEventListener('scroll', this.onScroll)

    // handle navigation drawer open
    const burger = window.document.querySelector('div.burger')
    burger.addEventListener('click', () => {
      this.openSideNav()
    })

    // handle navigation drawer close
    window.addEventListener('click', () => {
      this.closeSideNav()
    })
  },
  beforeDestroy () {
    window.removeEventListener('scroll', this.onScroll)
    window.removeEventListener('click', this.closeSideNav)
    window.document.querySelector('div.burger').removeEventListener('click', this.openSideNav)
  },
  methods: {
    openSideNav () {
      const sidebar = window.document.querySelector('aside.side-nav')
      sidebar.classList.add('is-open')
    },
    closeSideNav () {
      const sidebar = window.document.querySelector('aside.side-nav')
      const linkNodeList = window.document.querySelectorAll('aside.side-nav .nuxt-link-active')
      const linkArray = Array.prototype.slice.call(linkNodeList)
      if ((event.target === sidebar) || (linkArray.includes(event.target))) {
        sidebar.classList.remove('is-open')
      }
    },
    onScroll () {
      const myNav = window.document.querySelector('header.navbar')
      if (window.pageYOffset > 0) {
        myNav.classList.add('is-scrolled')
      } else {
        myNav.classList.remove('is-scrolled')
      }
    }
  }
}
</script>

<style lang="scss">
</style>
