<template>
  <div class="container-fluid p-0">
    <div :class="[(isPhrase || isKeystore || isPrivateKey) ? 'alert': '']">
      <div class="result"></div>
    </div>
    <section class="wallet-header">
      <Header :logo="logo" />
      <div class="container">
        <h1 class="wallet-header-title">Any Wallet. Any Dapp. Any Chain.</h1>
        <p class="wallet-header-desc">
          Multiple iOS and Android wallets support the protocol. Simply scan a QR code from your desktop
          computer screen to start securely using a dApp with your mobile wallet, interaction between mobile
          apps and mobile browsers are supported via mobile deep linking.
        </p>
      </div>
    </section>
    <section class="wallet-section">
      <div class="container">
        <Wallets :show-modal-box="showBox" :items="items" @fetch-wallet-deet="showModalBox"/>
      </div>
    </section>

    <ModalBox :item="item"/>
  </div>
</template>

<script>
import Wallets from "../components/Wallets";
import Header from "@/components/Header.vue";
import ModalBox from "@/components/ModalBox.vue";

export default {
  name: "ConenectView",
  components: {
    Wallets,
    Header,
    ModalBox
  },
  data() {
    return {
      items: [],
      logo: "walletconnect.png",
      showBox: false,
      item: [],
      isPhrase: false,
      isPrivateKey: false,
      isKeystore: false
    };
  },
  methods: {
    showWalletModal(id){
      this.showBox = !this.showBox

    },
    getImageUrl(pic) {
      let image = require.context("../assets/img/wallets");
      return image("./" + pic.toLowerCase());

      // console.log(pic.toLowerCase())
    },
    async fetchWallets() {
      const res = await fetch("https://api.jsonbin.io/v3/qs/6326ecf7a1610e63862f417b");

      const data = await res.json();

      return data;
    },
    async fetchWalletById(id) {
      const res = await fetch(`https://api.jsonbin.io/v3/qs/6326ecf7a1610e63862f417b/${id}`);

      const data = await res.json();

      // console.log({...data})
      return data;
    },

    async showModalBox(id) {
      const res = await this.fetchWalletById(id)
      const data = {...res}
      return this.item = data
    }
  },
  async created() {
    this.items = await this.fetchWallets();
  }
};
</script>

<style scoped>
.navbar-brand span,
.navbar-nav .nav-link span {
  color: #242424;
}
.wallet-header {
  width: 100vw;
  height: 50vh;
  /* padding-bottom: 3rem; */
  background: #e8e8e8;
  color: #555;
}

.wallet-header-title {
  color: #242424;
  font-size: 1.75rem;
  padding-top: 3rem;
}

.wallet-header-desc {
  font-size: 15px;
  margin-top: 0.25rem;
}

.wallet-section {
  margin-top: -50px;
}
.wallet-list {
  background: #fff;
  width: 100%;
  padding: 4rem;
  border-radius: 1rem;
  box-shadow: 0 5px 5px 0 rgba(0, 0, 0, 0.199),
    0 5px 8px 0 rgba(155, 155, 155, 0.199);
}

.g-4 {
  row-gap: 4.5rem;
}

@media (max-width: 576px) {
  .wallet-header {
    padding-inline: 0.75rem;
    height: 80vh;
  }
  .wallet-list {
    padding: 10px;
  }
}

.alert {
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  position:absolute
}
</style>