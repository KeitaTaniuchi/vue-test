<template>
  <div>
    <p>{{ `鉛筆とノートの合計金額は、${totalPrice}円` }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          name: "鉛筆",
          price: 300,
          quantity: 1,
        },
        {
          name: "ノート",
          price: 400,
          quantity: 2,
        },
      ],
    };
  },
  computed: {
    totalPrice: function () {
      return this.items.reduce((sum, item) => {
        return sum + item.price * item.quantity;
      }, 0);
    },
  },
};
</script>