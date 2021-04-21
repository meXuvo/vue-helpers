<template>
  <div>
      <div :class="{'bg-gray-300':value, 'bg-gray-600':!value,}" class="w-20 h-10 rounded-full relative ">
          <span role="checkbox" @click="toggleSwitch"  :class="{ 'translate-x-11': value }" class=" cursor-pointer transition duration-300 ease-in-out absolute bg-gray-100 h-8 rounded-full transform translate-x-1 translate-y-1 w-8"></span>
      </div>
  </div>
</template>

<script>
export default {
    props:{
        value:{
            type:Boolean,
            require:true
        }
    },
    methods:{
        toggleSwitch(){
            this.$emit('input', !this.value)
        }
    }
}
</script>

<style>

</style>