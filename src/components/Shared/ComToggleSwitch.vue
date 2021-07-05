<template>
    <div v-if="name === 'deep'" @click="toggleSwitch()" :class="{'bg-gray-300':!value, 'bg-gray-600':value,}" class="transiton duration-500 ease-in-out w-20 h-10 rounded-full relative ">
        <span :class="{ 'translate-x-11 bg-gray-100': !value }" class=" cursor-pointer transition-transform duration-500 ease-in-out absolute bg-white h-8 rounded-full transform translate-x-1 translate-y-1 w-8"></span>
    </div>
    <div v-else-if="name === 'light'" @click="toggleSwitch()" :class="{'bg-gray-400':!value, 'bg-blue-600':value,}" class=" transiton duration-500 ease-in-out shadow w-10 h-5 rounded-full relative ">
        <span   :class="{ 'translate-x-5 bg-gray-200': !value, '-translate-x-2 bg-white' :value}" class="shadow -top-2 cursor-pointer absolute transition-transform duration-500 ease-in-out  h-7 rounded-full transform translate-y-1 w-7"></span>
    </div>
</template>
<script>
export default {
    props:{
        name:{
            type:String,
        },
        value:{
            type:Boolean,
            require:true
        }
    },
//    model:{
//        prop:'value',
//        event:'input'
//    },
    methods:{
        toggleSwitch(){
            this.$emit('input', !this.value)
        }
    }
}
</script>

<style>

</style>