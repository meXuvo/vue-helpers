<template>
  <div>
    <div>
      <ComInput InputClasses="border w-1/2 border-blue-500 focus:border-transparent focus:outline-none focus:ring-2 focus:ring-red-500 rounded"
                name="first_name"
                type="password"
                v-model="firstName"
                label="first Name"
                :mandatory-field="true"/>
    </div>
    <div class="mt-10">
      <com-toggle-switch v-model="goodPerson" @input="goodPerson" ></com-toggle-switch>
    </div>
  </div>
</template>
<script>
import ComInput from "./Shared/ComInput";
import ComToggleSwitch from './Shared/ComToggleSwitch.vue';
export default {
  name: "test",
  components:{
    ComInput,
    ComToggleSwitch
  },
  data(){
    return{
      firstName:'',
      email:'',
      number:'',
      goodPerson:true

    }
  }
}
</script>

<style scoped>

</style>
