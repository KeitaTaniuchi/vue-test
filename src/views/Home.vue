<template>
  <div class="about">
    <p>{{ text }}</p>
    <p>{{ showMsg() }}</p>
    <p>{{ count }}</p>
    <button v-on:click="sayHello">挨拶</button>
    <button @click="countUp(10)">10増やす</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: "",
      count: 0,
    };
  },
  methods: {
    // メソッド名: function() {
    //      処理
    // },
    sayHello: function () {
      this.text = "Hello";
    },
    showMsg: function () {
      return "ボタンを押してね";
    },
    countUp: function (value) {
      this.count += value;
    },
  },
};
</script>