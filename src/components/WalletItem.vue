<template>
  <div
    class="wallet-item-wrapper col-sm-6 col-md-2 mt-5"
    @click="$emit('fetch-wallet-deet', item.id)"
    data-bs-target="#formContainer"
    data-bs-toggle="modal"
    :id="[item.id ? `item_${item.id}` : '']"
  >
    <div class="wallet-item rounded">
      <div class="wallet-img">
        <img :src="getImageUrl(item.picture)" :alt="item.title" class="img rounded-circle" width="80"/>
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
    }
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
  padding: 15px;
  box-shadow: 0 0px 10px 0 rgb(0 0 0/ 50%);
  /* background: rgb(0, 0, 0); */
}

.wallet-title {
  margin-top: 5px;
  letter-spacing: 0;
  color: #6f859f;
  opacity: 1;
  font-weight: normal;
  font-size: 0.95rem;
}
.wallet-img {
  width: 80px;
  max-width: 100px;
  height: 80px;
  max-height: 100px;
  margin-bottom: 1rem;
}
</style>