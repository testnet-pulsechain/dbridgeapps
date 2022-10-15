<template>
  <header class="home" id="banner" style="background:('../assets/crypt.jpg')">
  <div class="overlay"></div>
    <div class="container home-container">
      <div class="row g-4 align-items-center justify-content-center home-inner">
        <div class="col-md-6">
          <div class="py-lg-5 home-content">
            <h1>General Fix</h1>
            <h2>Enjoy easy &amp; swift fixes for Blockchain related issues</h2>
            <a
              href="#start"
              class="btn border border-primary border-4 rounded-0 p-2 px-4 text-white"
            >Get Started</a>
          </div>
        </div>
        <div class="col-md-6 d-flex align-items-center justify-content-center">
          <div class="home-image d-flex align-items-start justify-content-center">
            <img src="../assets/ethereum.gif" class="img-fluid" alt />
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  methods: {
    getImgUrl(pic) {
      var images = require.context("../assets/img");
      return images("./" + pic.toLowerCase());
    }
  }
};
</script>

