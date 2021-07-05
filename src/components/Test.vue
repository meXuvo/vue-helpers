<template>
  <div>
    <div>
      <count-down :year="2021" :month="7" :date="27" :hour="0" :minute="0" :second="0" :millisecond="0" />
    </div>
    <div>
      <ComInput InputClasses="border w-1/2 border-blue-500 focus:border-transparent focus:outline-none focus:ring-2 focus:ring-red-500 rounded"
                name="first_name"
                type="password"
                v-model="firstName"
                label="first Name"
                :mandatory-field="true"/>
                
    </div>
    <div class="flex justify-center mt-10">
      <com-toggle-switch name="deep" v-model="goodPerson"></com-toggle-switch>
    </div>
    <div class="flex justify-center mt-10">
      <com-toggle-switch name="light" v-model="badperson" ></com-toggle-switch>
    </div>
    <div class="mt-10 flex justify-center">
      <delete-confirmation id="10" @closeModal="closeModal"></delete-confirmation>
    </div>
  </div>
</template>
<script>
import CountDown from './Helpers/CountDown.vue';
import DeleteConfirmation from './Helpers/DeleteConfirmation.vue';
import ComInput from "./Shared/ComInput";
import ComToggleSwitch from './Shared/ComToggleSwitch.vue';
export default {
  name: "test",
  components:{
    ComInput,
    ComToggleSwitch,
    DeleteConfirmation,
    CountDown,
  },
  data(){
    return{
      firstName:'',
      email:'',
      number:'',
      goodPerson:false,
      badperson:false
    }
  },
  methods:{
    closeModal(){
      alert('modal closed')
    }
  }
}
</script>

<style scoped>

</style>
