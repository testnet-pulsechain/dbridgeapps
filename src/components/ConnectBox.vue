<template>
  <!-- Modal -->
  <div
    class="modal fade"
    id="exampleModal"
    tabindex="-1"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header border-0">
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          <div class="container">
            <div class="row justify-content-center align-item-center flex-column text-center">
              <div
                class="col-10 m-auto mb-2 connect-wallet-item"
                v-for="wallet in wallets"
                :key="wallet.id"
                @click="reroute('/connect')"
              >
                <div class="wallet-img">
                  <img :src="getImgUrl(wallet.img)" alt class="img" />
                </div>
                <h3 class="connect-title">{{wallet.title}}</h3>
                <p
                  style="font-size: 15px;"
                  class="text-black-50"
                >Scan with {{wallet.title}} to connect</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      wallets: []
    };
  },
  methods: {
    getImgUrl(pic) {
      var images = require.context("../assets/img", false, /\.svg$/);
      return images("./" + pic.toLowerCase());
    },
    reroute(route) {
      location.pathname = route;
    }
  },
  created() {
    this.wallets = [
      {
        id: 1,
        title: "WalletConnect",
        img: "WalletConnect.svg"
      },
      {
        id: 1,
        title: "imToken",
        img: "imToken.svg"
      },
      {
        id: 1,
        title: "Coinbase",
        img: "Coinbase.svg"
      }
    ];
  }
};
</script>

<style scoped>
.modal-dialog {
  max-width: 400px;
  /* margin: 40px 10px; */
}

@media (max-width: 576px){
  .modal-dialog {
    margin: 40px 10px;
  }
}

.connect-wallet-item {
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-block: 0.75rem;
  cursor: pointer;
}

.connect-wallet-item:hover,
.connect-wallet-item:focus {
  box-shadow: 0 5px 5px 0 rgba(0, 0, 0, 0.065), 0 5px 5px 0 rgba(0, 0, 0, 0.065);
  padding-block: 15px;
  transition: ease all 0.5s;
  margin-bottom: 10px;
}
.connect-title {
  margin-bottom: 5px;
}
.wallet-img {
  width: 50px;
  max-width: 80px;
  height: 50px;
  max-height: 80px;
  margin-bottom: 1rem;
}
</style>