<template lang="pug">
vue-tel-input(  @input="shownum")
  
</template>

<script setup>
const phone = ref(null);
function shownum(event, object) {
  if (object?.number) {
    phone.value = object.number;
    console.log(object.number);
  }
}
</script>

<style></style>
