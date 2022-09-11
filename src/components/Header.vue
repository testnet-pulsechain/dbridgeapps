<template>
  <header class="home py-2">
      <nav class="navbar">
        <div class="container">
          <a class="navbar-brand" href="#">
            <img
              :src="getImgUrl(logo)"
              alt="PulseChain Bridge"
              :width="[showLogoTitle ? 50 : '150']"
              :height="[showLogoTitle ? 30 : '30']"
              class="d-inline-block align-text-top"
            />
            <span class="ps-lg-2 fs-5 fs-sm-6" v-show="showLogoTitle">PulseChain Bridge</span>
          </a>
          <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <a class="nav-link px-2" aria-current="page" href="#">
                <span class="bi bi-list fs-3"></span>
              </a>
            </li>
          </ul>
        </div>
      </nav>
    </header>
</template>

<script>
export default {
    name: 'Header',
    props: {logo: String, showLogoTitle: Boolean},
    methods:{
        getImgUrl(pic) {
            var images = require.context("../assets/img");
            return images("./" + pic.toLowerCase());
        },
    }
}
</script>

