<template>
  <div class="container">
    <h1>
      Contact Us
    </h1>
    <form class="contact-form">
      <div class="form-element">
        <label for="name">Full Name</label>
        <input id="name" type="text" name="name">
      </div>
      <!--  -->
      <div class="form-group">
        <div class="form-element">
          <label for="email">Email</label>
          <input id="email" type="text" name="email">
        </div>
        <!--  -->
        <div class="form-element">
          <label for="phone">Phone</label>
          <input id="phone" type="text" name="phone">
        </div>
      </div>
      <!--  -->
      <div class="form-group">
        <div class="form-element">
          <label for="company">Company Name</label>
          <input id="company" type="text" name="company">
        </div>
        <!--  -->
        <div class="form-element">
          <label for="location">Location</label>
          <input id="location" type="text" name="location">
        </div>
      </div>
      <!--  -->
      <div class="form-element">
        <label for="subject">Subject</label>
        <input id="subject" type="text" name="subject">
      </div>
      <!--  -->
      <div class="form-element">
        <label for="message">Message</label>
        <textarea id="message" name="message" />
      </div>
      <input type="submit" value="Submit">
    </form>
    <div class="location">
      <div class="address">
        <p class="title">Aura LaserFab Pvt. Ltd.</p>
        <p>Gate No. 1021, Pune - Bangalore Highway</p>
        <p>Near Pune, Shirval</p>
        <p>Dist. Satara - 412801</p>
        <p>Maharashtra, India</p>
      </div>
      <div class="info-text">
        <div class="bold">Phone: </div>
        <div class="regular">+91 2169 244545, +91 2169 244546</div>
      </div>
      <div class="info-text">
        <div class="bold">Email: </div>
        <div class="regular">sales@auralaser.net | laser@auralaser.net</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  head () {
    return { title: 'Contact Us' }
  }
}
</script>

<style lang="scss">

.form-element {
  padding: .5em;
}
label,
input,
textarea {
  display: block;
  width: 100%;

}
label {
  padding-bottom: .35em;
}
.form-group {
  display: flex;
  .form-element {
    width: 50%;
  }
}
.info-text {
  display: flex;

  .bold {
    font-weight: bold;
  }
}
</style>
