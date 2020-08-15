<template>
  <div class="flex flex-col items-center">
    <h1 class="font-bold pb-1 ">Phone number</h1>
    <Telephone class="my-2 p-1" template="+(XXX)-XXX-XXX-XXX"></Telephone>
    <Telephone class="my-2 p-1" template="XX.XX.XX.XX.XX"></Telephone>
  </div>
</template>

<script>

import Telephone from "@/components/Telephone"
export default {
  name: "Form",
  components:{
    Telephone,
  }
}
</script>

<style scoped>

</style>