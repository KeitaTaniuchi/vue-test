<template>
  <div class="about">
    <h1>This is an about page</h1>
    <ol class="use-computed">
      <li>{{ computedNumber }}</li>
      <li>{{ computedNumber }}</li>
      <li>{{ computedNumber }}</li>
    </ol>
    <ol class="use-methods">
      <li>{{ methodsNumber() }}</li>
      <li>{{ methodsNumber() }}</li>
      <li>{{ methodsNumber() }}</li>
    </ol>
  </div>
</template>
    
<script>
export default {
  computed: {
    computedNumber: function () {
      return Math.random(); //0〜1のランダムな数字を生成
    },
  },
  methods: {
    methodsNumber: function () {
      return Math.random(); //0〜1のランダムな数字を生成
    },
  },
};
</script>