<template>
  <div class="container-fluid bg-wallet">
    <Header :logo="logo" :showLogoTitle="showLogoTitle"/>
    <section class="connect mb-5">
      <div class="container d-flex my-5 justify-content-center">
        <div class="connect-box">
          <div class="connect-img">
            <div class="connect-icon">
              <i class="bi bi-folder"></i>
            </div>
          </div>
          <div class="connect-desc">
            <h3 class="connect-title">Connect Wallet</h3>
            <p>To get started, connect your wallet</p>
            <!-- data-bs-toggle="modal"
              data-bs-target="#exampleModal" -->
            <button
            @click="reroute('/connect')"
              class="btn btn-primary px-5 py-2 fw-bold"
              
            >Connect</button>
          </div>
        </div>
      </div>
    </section>
    <footer class="footer mt-5" id="footer">
      <div class="container">
        <div class="d-sm-flex justify-content-between align-items-center mb-3">
          <div class="fs-6 fw-500">Built by the PulseChain Community</div>
          <div class="home-social d-flex justify-content-start align-items-center">
            <a href class="nav-link footer_link pe-3">
              <i class="bi bi-twitter"></i>
            </a>
            <a href class="nav-link footer_link">
              <i class="bi bi-telegram"></i>
            </a>
          </div>
        </div>
        <div class="d-sm-flex justify-content-between align-items-center mb-3 mt-lg-5">
          <div class="mb-3 d-flex align-items-center flex-sm-column flex-lg-row">
            <a
              href="#"
              class="nav-link footer_link pe-4"
              style="width:20ch;  line-height:2;font-size:14px;"
              target="_blank"
            >PulseChain Testnet Block: 0</a>
            <a
              href="#"
              class="nav-link footer_link"
              style="width:15ch; line-height:2;font-size:14px;"
              target="_blank"
            >Rinkeby Testnet Block: 0</a>
          </div>
          <div>
            <p>v.a86cb5e</p>
          </div>
        </div>
        <p>
          <a
            href="#"
            class="footer_link text-white text-decoration-none"
            style="font-size:14px;"
          >/ipfs/QmTMdE5NLjamQVD65fNBPLrBEqmy8mS2umX7wL62q7HFNc</a>
        </p>
      </div>
    </footer>

    <ConnectBox />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import ConnectBox from "@/components/ConnectBox.vue";

export default {
  name: "HomeView",
  components: {
    Header,
    ConnectBox
  },
  data() {
    return {
      logo: "logo.726505f2.svg",
      showLogoTitle: true
    };
  },
  methods:{
    reroute(route) {
      location.pathname = route;
    }
  }
};
</script>


<style>
.home {
  position: relative;
}

.bg-wallet {
  padding: 5px 25px 0 25px;
  margin: 0px;
  overflow-x: hidden;
  font-family: var(--chakra-fonts-body);
  width: 100%;
  min-height: 100vh;
  position: relative;
  background-image: url("../assets/img/backgroundPulse-sm.ff064d7d.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center center;
}

.navbar-brand {
  text-align: center;
  display: flex;
  align-items: center;
  padding-right: 1rem;
}
.navbar-brand span,
.footer .footer-link,
.footer .nav-link,
.footer {
  color: rgb(223, 228, 237);
}
.navbar-nav {
  flex-direction: row;
}

.navbar-nav .nav-link span {
  color: #fff;
}

.connect-box {
  width: calc(100% - 2rem);
  height: 300px;
  background: #fff;
  padding: 2rem;
  display: flex;
  flex-flow: column nowrap;
  overflow: hidden;
  align-items: center;
  justify-content: center;
  text-align: center;
  border-radius: 1rem;
  box-shadow: rgb(204 218 238 / 80%) 0px 1rem 2rem;
  max-width: 31rem;
}

.connect-img {
  width: 80px;
  height: 80px;
  background: #0d6efd;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  padding: 1.25rem 0;
}

.connect-icon i {
  font-size: 1.6rem;
  font-weight: bold;
  color: #fff;
}

.connect-desc {
  margin-block: 1rem;
}

.connect-title {
  font-size: 1.25rem;
  margin-bottom: 1em;
  color: #242424;
}
.footer {
  margin-top: 1rem;
}

.text-light {
  color: #333;
}
</style>