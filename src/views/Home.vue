<template>
  <div>
    <Header :username="name" v-model="InputData.condition">
      <template v-slot:message>
        <p>Let's enjoy programming!</p>
      </template>
    </Header>
    <Body @add="add1"></Body>
    <Body @add="add2"></Body>
    <p>total : {{ totalcount }}</p>
    <p>condition : {{ InputData.condition }}</p>
    <button @click="componentName = 'Header'">Header</button>
    <button @click="componentName = 'Body'">Body</button>
    <keep-alive>
      <component :is="componentName"></component>
    </keep-alive>
  </div>
</template>

<style scoped>
p {
  color: green;
}
</style>

<script>
import Header from "../components/Header.vue";
import Body from "../components/Body.vue";

export default {
  components: {
    Header,
    Body,
  },
  data() {
    return {
      name: "keita",
      count1: 0,
      count2: 0,
      totalcount: 0,
      InputData: {
        condition: "",
      },
      componentName: "Header",
    };
  },
  methods: {
    add1(count) {
      this.count1 = count;
      this.totalcount = this.count1 + this.count2;
    },
    add2(count) {
      this.count2 = count;
      this.totalcount = this.count1 + this.count2;
    },
  },
};
</script>
