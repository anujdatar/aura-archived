<template>
  <div class="hero-image" :style="bgImage">
    <div class="hero-text">
      <h1>
        {{ title }}
      </h1>
      <p>
        {{ text }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    image: {
      type: String,
      required: true
    },
    title: {
      type: String,
      default: 'We make stuff'
    },
    text: {
      type: String,
      default: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Dolorem, laborum.'
    }
  },
  computed: {
    bgImage () {
      return {
        '--img-url': 'url(' + this.image + ')'
      }
    }
  }
}
</script>

<style lang="scss">
.hero-image {
    z-index: -1;
    background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), var(--img-url);
    height: 100vh;
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    padding: 0;
    // margin-top: -56px;
    //top: 0;
  }
  .hero-text {
    text-align: center;
    position: relative;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: white;

    p {
      text-align: center;
    }
  }
</style>
