<template>

    <div class="wallet-list">
    <div class="row">
      <WalletItem  :key="item.id" v-for="item in items" :item="item" @fetch-wallet-deet="$emit('fetch-wallet-deet', item.id)" />
    </div>
  </div>

</template>

<script>
import WalletItem from "./WalletItem.vue";

export default {
  name: "Wallets",
  props: { items: Array },
  components: {
    WalletItem
  },
  emits: ["show-wallet-logo", 'fetch-wallet-deet']
};
</script>

<style>
</style>