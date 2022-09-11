<template>
  <div class="wallet-item-wrapper col-6 col-md-4" @click="$emit('fetch-wallet-deet', item.id)" data-bs-target='#formContainer' data-bs-toggle='modal' :id="[item.id ? `item_${item.id}` : '']">
    <div class="wallet-item">
      <div class="wallet-img">
        <img :src="getImageUrl(item.picture)" :alt="item.title" class="img" />

      </div>
      <div class="wallet-desc">
        <h3 class="wallet-title">{{item.title}}</h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "WalletItem",
  props: { item: Object },
  methods: {
    getImageUrl(pic) {
      let image = require.context("../assets/img/wallets");
      return image("./" + pic.toLowerCase());
    },
  }
};
</script>

<style scoped>
.wallet-item {
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  padding-block: 15px;
}

.wallet-item:hover,
.wallet-item:focus {
  box-shadow: 0 2px 2px 0 rgba(0, 0, 0, 0.015), 0 5px 5px 0 rgba(0, 0, 0, 0.019);
  transition: ease all 0.5s;
  background: #f8f6f696;
}
.wallet-title {
  margin-top: 5px;
  letter-spacing: 0;
  color: #6f859f;
  opacity: 1;
  font-weight: normal;
  font-size:0.95rem;
}
.wallet-img {
  width: 80px;
  max-width: 100px;
  height: 80px;
  max-height: 100px;
  /* margin-bottom: 1rem; */
}
</style>