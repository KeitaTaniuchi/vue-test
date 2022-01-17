<template>
  <div>
    <ul v-for="(item, key) in items" :key="key">
      <li>
        <span>{{ item.name }}</span
        >&nbsp;|&nbsp; <span>{{ item.price }}円</span>&nbsp;*&nbsp;
        <span><input type="number" v-model="item.quantity" />個</span
        >&nbsp;=&nbsp;
        <span>{{ item.price * item.quantity }}円</span>
      </li>
    </ul>
    <div>合計金額：{{ totalPriceWithTax }}円(税込)</div>
    <button @click="doBuy">購入する</button>
  </div>
</template>
    
<script>
export default {
  data() {
    return {
      items: [
        { name: "レモン", price: 100, quantity: 2 },
        { name: "りんご", price: 200, quantity: 1 },
        { name: "メロン", price: 800, quantity: 1 },
      ],
    };
  },
  methods: {
    doBuy: function () {
      window.alert(
        this.totalPriceWithTax + "円のお買い上げです。ありがとうございました。"
      );
    },
  },
  computed: {
    // 合計金額
    totalPrice: function () {
      return this.items.reduce(function (sum, item) {
        return sum + item.price * item.quantity;
      }, 0);
    },
    // 合計金額(税込)
    totalPriceWithTax: function () {
      return Math.floor(this.totalPrice * 1.08);
    },
  },
};
</script>