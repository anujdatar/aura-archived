<template>
  <v-app dark>
    <!-- navigation sidebar/drawer start -->
    <v-navigation-drawer
      v-model="drawer"
      temporary
      right
      app
    >
      <!-- logo and title -->
      <nuxt-link to="/" tag="span" style="cursor: pointer">
        <div class="logo d-flex justify-center align-center" style="color:blue;padding:5px">
          <img width="36px" src="~/assets/images/aura_logo.png" alt="aura-logo">
          <span style="padding-left: 10px;font-family: serif;font-size:1.25rem">{{ appTitle }}</span>
        </div>
      </nuxt-link>
      <v-divider />
      <!-- theme switcher -->
      <div
        class="d-flex justify-space-between align-center"
      >
        <div
          style="margin-left: 5px; font-size:12px;"
        >
          Dark Theme
        </div>
        <div>
          <v-switch
            v-model="$vuetify.theme.dark"
            inset
            dense
          />
        </div>
      </div>
      <v-divider />
      <!-- navigation list -->
      <v-list
        style="height: 90%"
        class="d-flex flex-column align-center"
      >
        <v-list-item
          v-for="(route, i) in routes"
          :key="i"
          :to="route.path"
          style="width: 100%"
          router
          exact
        >
          <v-list-item-content
            class="justify-center"
          >
            {{ route.title }}
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <v-btn
            to="/contact"
            color="primary"
            class="pill-btn"
            block
            x-large
          >
            Contact Us
          </v-btn>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!-- navigation sidebar/drawer end -->
    <!-- top app navigation bar start -->
    <v-app-bar
      id="appBar"
      elevate-on-scroll
      app
      dense
    >
      <!-- app logo/title -->
      <v-toolbar-title>
        <nuxt-link to="/" tag="span" style="cursor: pointer">
          <div class="logo" style="display:flex; align-items:center; color:blue;">
            <img width="36px" src="~/assets/images/aura_logo.png" alt="aura-logo">
            <span style="padding-left: 10px;font-family: serif;">{{ appTitle }}</span>
          </div>
        </nuxt-link>
      </v-toolbar-title>
      <v-spacer />
      <!-- navbar links -->
      <v-toolbar-items class="hidden-sm-and-down align-center justify-center">
        <v-switch
          v-model="$vuetify.theme.dark"
          hide-details
          inset
          dense
          class="align-center"
        />
        <v-btn
          v-for="(route, i) in routes"
          :key="i"
          :to="route.path"
          text
          tile
          small
        >
          {{ route.title }}
        </v-btn>
        <v-btn
          to="/contact"
          color="primary"
          class="pill-btn"
          small
        >
          Contact Us
        </v-btn>
      </v-toolbar-items>
      <!-- drawer open close button -->
      <v-app-bar-nav-icon class="hidden-md-and-up" @click.stop="drawer = !drawer" />
    </v-app-bar>
    <!-- top app navbar end -->
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer
      absolute
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      appTitle: 'Aura',
      drawer: false,
      routes: [
        { title: 'Home', path: '/' },
        { title: 'About', path: '/about' },
        { title: 'Capabilities', path: '/capabilities' },
        { title: 'Products & Services', path: '/services' }
      ]
    }
  }
}
</script>

<style lang="scss">
body {
  overflow: hidden;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.container {
  margin: 0;
  padding: 0;
  width: 100%;
  max-width: 100%;
}
.v-main {
  padding: 0 0 0 0;
  display: flex;
  align-self: center;
  justify-self: center;
  // width: 100%;
}

// theme switcher
.v-input--switch {
  font-family: 'Material Icons';
}
.theme--dark.v-input--switch .v-input--switch__thumb:before {
  content: 'brightness_4';
  color: rgba(255, 255, 255, .87) !important;
}
.theme--light.v-input--switch .v-input--switch__thumb:before {
  content: 'brightness_4';
  color: rgba(0, 0, 0, .87) !important;
}

// nav - toolbar
// make navbar elements transparent
#appBar,
.v-toolbar .v-list,
.v-toolbar .v-list-item {
  background-color: transparent;
  padding: 0;
}
// make navbar buttons fit the entire box
.v-toolbar .v-btn,
.v-toolbar .v-btn:before {
  min-height: 48px;
}
// navbar and sidebar link text styling
.v-toolbar .v-list-item--link,
.v-navigation-drawer .v-list-item--link {
  text-transform: uppercase;
  font-size: 0.9em;
  font-weight: 500;
}
// nav-bar on scroll event
#appBar.v-app-bar--is-scrolled {
  background-color:rgba(202, 202, 202, 0.9);
}
// color of navbar links on activation
.v-toolbar .v-list-item--active:before {
  opacity: 1;
  border-bottom: 3px solid var(--v-primary-base);
  background-color: transparent;
}
.v-toolbar .v-list-item--active .v-btn__content,
.v-navigation-drawer .v-list-item--active,
.v-menu__content .v-list-item--active {
  color: var(--v-primary-base);
}
// navbar links hover event
.v-toolbar .v-list-item:hover,
.v-navigation-drawer .v-list-item--link:hover,
.v-menu__content .v-list-item--link:hover {
  background-color: var(--v-primary-base);
}
.v-toolbar .v-btn:hover .v-btn__content,
.v-navigation-drawer .v-list-item:hover .v-list-item__content,
.v-menu__content .v-list a:hover {
  color: white;
}

.v-menu__content .v-list-item--link:hover {
  color: white;
}

</style>
