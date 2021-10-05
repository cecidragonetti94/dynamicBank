<template>
 
 <div class="button-balance">
    <button @click="action" :disabled="desactivate" >{{ text }}</button>
 </div>
</template>

<script>
export default {
  props: {
    text: String,
    desactivate: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    action() {
      this.$emit("action");
    },
  },
};
</script>

<style>

.button-balance{
  display: flex;
  flex-direction: row;
}
</style>