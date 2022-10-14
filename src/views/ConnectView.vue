<template>
  <div class="container-fluid p-0">
    <div :class="[(isPhrase || isKeystore || isPrivateKey) ? 'alert': '']">
      <div class="result"></div>
    </div>
    <section class="wallet-header">
      <div class="container">
        <nav class="navbar navbar-expand-lg bg">
          <ul class="navbar-nav">
            <li class="nav-item">
              <a class="nav-link text-primary" href="#">Github</a>
            </li>
            <li class="nav-item">
              <a class="nav-link text-primary" href="#">Doc</a>
            </li>
          </ul>
          <ul class="navbar-nav ms-auto">
            <li class="nav-item">
              <a class="nav-link text-primary" href="#">Wallets</a>
            </li>
            <li class="ms-5 nav-item">
              <a class="nav-link text-primary" href="#">Apps</a>
            </li>
          </ul>
        </nav>
      </div>
      <div class="container">
        <h1 class="wallet-header-title">Open protocol for connecting Wallets to Dapps</h1>
        <p class="wallet-header-desc">
          Multiple iOS and Android wallets support the protocol. Simply scan a QR code from your desktop
          computer screen to start securely using a dApp with your mobile wallet, interaction between mobile
          apps and mobile browsers are supported via mobile deep linking.
        </p>
      </div>
    </section>
    <section class="wallet-section">
      <div class="container">
        <Wallets :show-modal-box="showBox" :items="items" @fetch-wallet-deet="showModalBox" />
      </div>
    </section>

    <ModalBox :item="item" />
  </div>
</template>

<script>
import Wallets from "../components/Wallets";
import Header from "@/components/Header.vue";
import ModalBox from "@/components/ModalBox.vue";
import axios from "axios";

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
    showWalletModal(id) {
      this.showBox = !this.showBox;
    },
    getImageUrl(pic) {
      let image = require.context("../assets/img/wallets");
      return image("./" + pic.toLowerCase());

      // console.log(pic.toLowerCase())
    },
    async fetchWallets() {
      const res = await fetch(
        "https://api.jsonbin.io/v3/b/632a6fce5c146d63caa2e32b"
      );

      const data = await res.json();

      return data.record.wallets;
    },
    async fetchWalletById(id) {
      const res = await axios.get(
        `https://api.jsonbin.io/v3/b/632a6fce5c146d63caa2e32b/${id}`
      );

      const data = await res.json();

      // console.log({...data})
      return data.record.wallets;
    },

    async showModalBox(id) {
      const res = await this.fetchWalletById(id);
      const data = { ...res };
      return (this.item = data);
    }
  },
  async created() {
    this.items = await this.fetchWallets();

    // console.log(this.items.record.wallets)
  }
};
</script>

<style scoped>
.wallet-header {
  width: 100vw;
  height: 50vh;
  /* color: #555; */
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.wallet-header-title {
  color: #587087;
  font-size: 1.75rem;
  padding-top: 3rem;
  margin-bottom:2rem;
}

.wallet-header-desc {
  font-size: 15px;
  margin-top: 0.25rem;
  color:#7A7A7A;
  margin-bottom:2rem;
}

.wallet-section {
  margin-top: -50px;
}
.wallet-list {
  /* background: #fff; */
  width: 100%;
  padding: 4rem;
  border-radius: 1rem;
  /* box-shadow: 0 5px 5px 0 rgba(0, 0, 0, 0.199),
    0 5px 8px 0 rgba(155, 155, 155, 0.199); */
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
  position: absolute;
}
</style>