<template>
  <input type="text" :placeholder="template" v-model="number"
         class="shadow  border rounded w-1/5 py-2 px-3 bg-gray-200 font-bold leading-tight focus:outline-none focus:shadow-outline"
  >
</template>

<script>
export default {
name: "Telephone",
  props: [
  'template'
  ],
  data : function (){
  return {
    number : '',
    format: '',
    regex:'^',
  }
  },
  mounted() {
    let x =1;
    this.format=this.template.replace(/X+/g, () => '$'+x++)
    this.template.match(/X+/g).forEach((char)=>
      this.regex+='(\\d{'+char.length+'})?'
    )
    console.log(this.regex)
  },
  watch:{
    number(){
        this.number = this.number.replace(/[^0-9]/g,'')
            //.replace(/^(\d{3})?(\d{3})?(\d{3})?(\d{3})?/g,  this.format)
            .replace(new RegExp(this.regex, 'g'),  this.format)
            .substr(0,this.template.length);

    }
  }
}
</script>

<style scoped>

</style>