<template>
  <div class="description_collapse">
    <p :class="{ 'truncate-3-lines': !isActive }"><slot></slot></p>
    <button :text="text" @click="open">{{text}}</button>
  </div>
</template>
<script setup>
import { ref } from "vue";
let text = ref('shiko më shumë');
let isActive = ref(false);

function open() {
    isActive.value = !isActive.value
    isActive.value ? text.value = "shiko më pak" : text.value = "shiko më shumë" 
}
</script>
<style scoped>
button {
  background-color: rgba(1,1,1,0);
  border: none;
  cursor: pointer;
  color: var(--paragraph-color);
  font-family: var(--paragraph-font);
  font-size: 0.9rem;
  text-decoration: underline;
}
.description_collapse{
    margin-top: 0.5rem;
}
.description_collapse p {
  font-size: 1rem;
}
</style>
