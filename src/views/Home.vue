
<template>
  <div class="about">
    <p>{{ number }}</p>
    <!-- 123 -->
    <p>{{ text }}</p>
    <!-- Hello -->
    <p>{{ bool }}</p>
    <!-- true -->
    <p>{{ arr }}</p>
    <!-- [ "a", "b", "c" ] -->
    <p>{{ arr[0] }}</p>
    <!-- a -->
    <p>{{ myFruits }}</p>
    <!-- [ { "name": "オレンジ", "price": 100 }, { "name": "レモン", "price": 200 }] -->
  </div>
</template>
<script>
export default {
  data() {
    return {
      number: 123,
      text: "Hello",
      bool: true,
      arr: ["a", "b", "c"],
      myFruits: [
        { name: "オレンジ", price: 100 },
        { name: "レモン", price: 200 },
        { name: "バナナ", price: 300 },
      ],
    };
  },
};
</script>