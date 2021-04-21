<template>
  <div class="flex-col flex">
    <label :class="LabelClasses" :for="name">{{label}} <sup v-if="mandatoryField && label" class="text-red-500">*</sup> </label>
    <input :id="name" :type="type" ref="input" :class="[{'border-red-500':errors},InputClasses]"  @input="$emit('input',$event.target.value)"  />
    <span v-if="errors" class="text-red-500">{{errors}}</span>
  </div>
</template>
<script>
export default {
  name: "InputCom.vue",
  props:{
    value:String,
    label:{
      type:String,
      require:true
    },
    mandatoryField:{
      type:Boolean,
      default:false
    },
    errors:{
      type:String,
    },
    type:{
      type:String,
      default: 'text',
    },
    name:{
      type:String,
      require: true
    },
    InputClasses:{
      type:String
    },
    LabelClasses:{
      type:String
    }
  },
}
</script>

<style scoped>

</style>
