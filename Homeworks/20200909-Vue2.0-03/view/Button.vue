<template>
    <button v-if="disabledSwicth==true" disabled>
      <slot name="btnTitle">默认禁用</slot>{{disabledSwicth}}
    </button>
    <button v-else v-on:click="btnClicked">
      <slot name="btnTitle">默认启用</slot>{{disabledSwicth}}
    </button>
</template>

<script>
export default {
  props: {
    disabled: {
      type: Boolean,
      default: false,
    },
  },
  data(){
    return {
      disabledSwicth:this.disabled,
    }
  },
  methods: {
    btnClicked() {
      console.log("Button Clicked !");
      this.$emit("click");
      this.disabledSwicth = !this.disabledSwicth;
      // setTimeout(() => {
      //   this.disabledSwicth = !this.disabledSwicth;
      // }, 3000);
    },
  },
};
</script>

<style>
</style>