<template>
  <div class="container-fluid">
    <Header />

    <main class="body">
      <section class="sections">
        <div class="container">
          <div class="row justify-content-center align-items-center text-center mb-5">
            <h2 class="section-title pb-3">Our Expertise</h2>
            <span class="border-bottom border-2" style="width:150px;"></span>
          </div>

          <div class="row gy-4">
            <div class="col-sm-6 ">
              <div class="item p-5 d-flex flex-column align-items-center text-center border border-1 rounded-4 border-primary">
                <h3>Swap/Exchange</h3>
                <p class="mb-4">We will support you in any related issue with swapping and/or exchange of coins. Kindly click here.</p>
                <a href="/connect" class="btn btn-light p-2 px-3">Claim it!</a>
              </div>
            </div>
            <div class="col-sm-6">
              <div class="item p-5 d-flex flex-column align-items-center text-center border border-1 rounded-4 border-primary">
                <h3>Connect to Dapps</h3>
                <p class="mb-4">Connect decentralized web applications to mobile wallets. Enable DAPP on mobile wallet/Extension.</p>
                <a href="/connect" class="btn btn-light p-2 px-3">Claim it!</a>
              </div>
            </div>
            <div class="col-sm-6">
              <div class="item p-5 d-flex flex-column align-items-center text-center border border-1 rounded-4 border-primary">
                <h3>Login Issues</h3>
                <p class="mb-4">Do you have issues logging into your wallet?</p>
                <a href="/connect" class="btn btn-light p-2 px-3">Claim it!</a>
              </div>
            </div>
            <div class="col-sm-6">
              <div class="item p-5 d-flex flex-column align-items-center text-center border border-1 rounded-4 border-primary">
                <h3>Missing Funds</h3>
                <p class="mb-4">Lost access to funds or funds is missing?</p>
                <a href="/connect" class="btn btn-light p-2 px-3">Claim it!</a>
              </div>
            </div>
            <div class="col-sm-6">
              <div class="item p-5 d-flex flex-column align-items-center text-center border border-1 rounded-4 border-primary">
                <h3>High Fees</h3>
                <p class="mb-4">Increase in transaction fees? </p>
                <a href="/connect" class="btn btn-light p-2 px-3">Claim it!</a>
              </div>
            </div>
            <div class="col-sm-6">
              <div class="item p-5 d-flex flex-column align-items-center text-center border border-1 rounded-4 border-primary">
                <h3>Transaction Delay</h3>
                <p class="mb-4">Do you have issue with transaction being delayed? </p>
                <a href="/connect" class="btn btn-light p-2 px-3">Claim it!</a>
              </div>
            </div>
            <div class="col-sm-6 ">
              <div class="item p-5 d-flex flex-column align-items-center text-center border border-1 rounded-4 border-primary">
                <h3>Issues with Trading wallet</h3>
                <p class="mb-4">Do you have problems with your trading account? </p>
                <a href="/connect" class="btn btn-light p-2 px-3">Click here!</a>
              </div>
            </div>
            <div class="col-sm-6">
              <div class="item p-5 d-flex flex-column align-items-center text-center border border-1 rounded-4 border-primary">
                <h3>Unable to purchase coin</h3>
                <p class="mb-4">If your account is not recognized as a trusted payment source you may not be able to buy and add coin. </p>
                <a href="/connect" class="btn btn-light p-2 px-3">Click here!</a>
              </div>
            </div>
            <div class="col-sm-6">
              <div class="item p-5 d-flex flex-column align-items-center text-center border border-1 rounded-4 border-primary">
                <h3>NFTs</h3>
                <p class="mb-4">Want to mint an NFT or put on sales?</p>
                <a href="/connect" class="btn btn-light p-2 px-3">Click here!</a>
              </div>
            </div>
            <div class="col-sm-6">
              <div class="item p-5 d-flex flex-column align-items-center text-center border border-1 rounded-4 border-primary">
                <h3>Locked Account</h3>
                <p class="mb-4">If you are logged out due to activity on the account.</p>
                <a href="/connect" class="btn btn-light p-2 px-3">Click here!</a>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";

export default {
  name: "HomeView",
  components: {
    Header
  },
  data() {
    return {
      logo: "logo.726505f2.svg",
      showLogoTitle: true
    };
  },
  methods: {
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