<template>
  <div id="app">
      <Button :[switchName]="disabled" v-slot:btnTitle v-on:click="hello(buttonName,$event)">{{switchName}}:</Button>
  </div>
</template>

<script>
import Button from "./view/Button";
export default {
  name: "App",
  components: {
    Button,
  },
  data(){return{
    disabled:false,
    switchName:"disabled",
    buttonName:"TestBtn",
  }},
  methods: {
    hello(m,e) {
      console.log(`Get Emit from : ${m}`);
    }
  },
};
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
