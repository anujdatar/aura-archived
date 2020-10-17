<template>
  <div class="container">
    <hero :image="heroImage" />
    <div class="page-container">
      <h1 class="page-title">
        An ISO 9001:2008 certified company
      </h1>
      <p>
        Situated near Pune, the engineering Capital of India, Aura LaserFab offers both manufacturing and job shopping services in the field of CNC Laser Cutting Services.
      </p>
      <div class="intro-card">
        <img src="~/assets/images/factory.jpg" alt="" srcset="">
        <p>
          Equipped with the latest machines of CNC Laser Cutting, Bending and Fabrication Aura manufactures a large variety of components with a mix of volumes. With the use of contemporary techniques of operations management we can deliver components in shorter lead time meeting universally acceptable quality standards. We manufacture products ranging from a precise laser cut –bent component to a complex welded and painted assembly using a variety of raw materials like carbon steel, stainless steel, aluminium, and special steels.
        </p>
      </div>
      <p>
        The team of Aura, comprising of 100+ qualified engineers and technicians, possesses a strong experience in the domains of development, marketing, engineering operations, projects and quality assurance.
      </p>
      <p>
        Aura Laser has presently spearheaded a major up scaling of its capacity in Metal Cutting &amp; fabrication with addition of workspace area, machineries like CNC Plasma Cutting, CNC Straightening, CNC Rolling and Robotic Welding to support its multi segmental growth.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      heroImage: require('~/assets/images/hero_home.jpg')
    }
  },
  head () {
    return { title: 'Home' }
  }
}
</script>

<style lang="scss">
// .container {
//   text-align: center;
// }

.page-title {
  text-align: center;
  margin: 20px;
}

.intro-card {
  // padding: 1em 0;
  img {
    float: left;
    max-width: 336px;
    margin-right: 10px;
  }
  p {
    text-align: justify;
    // padding-top: 10px;
    // text-justify: inter-word;
  }
}

@media screen and (max-width:768px) {
  .intro-card {
    display: flex;
    flex-direction: column;
    padding: 0;

    img {
      display: block;
      margin-left: auto;
      margin-right: auto;
    }
    p {
      padding-top: 10px;
    }
  }
}
</style>
