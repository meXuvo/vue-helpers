<template>
  <div>
      <input type="file" accept="image/*" class="hidden" ref="file" @change="change">
      <button @click="browse()">browse</button>
  </div>
</template>

<script>
export default {
    props:{ 
        value:File
    },
    methods:{
        browse(){
            this.$ref.file.click(); 
        },

        change(e){
            console.log(e)
            // ========================task pending========================
        }
    
    }

}
</script>

<style>

</style>