<template lang="pug">
vue-tel-input(  @input="shownum" @validate="validatecode"  :validCharactersOnly="true" :class="{ 'p-invali-input': !validphone }" defaultCountry="EG" )
//- small( class="p-error" id="text-error") {{ errorPhone }}
  
</template>

<script setup>
const phone = ref(null);
function shownum(event, object) {
  if (object?.number) {
    phone.value = object.number;
    console.log(object.number);
  }
}
const validphone = ref(true);
const errorPhone = ref("");
function validatecode(event) {
  console.log("validatecode", event.valid);
  if (event.valid === false) {
    validphone.value = false;
    errorPhone.value = "Enter valid phone";
  } else {
    validphone.value = true;
    errorPhone.value = "";
  }
}
</script>

<style scoped lang="scss">
.p-invali-input{
  border: 1px solid red;

}
</style>
