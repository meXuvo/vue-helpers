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
  </div>
</template>
<script>
import ComInput from "./Shared/ComInput";
export default {
  name: "test",
  components:{
    ComInput
  },
  data(){
    return{
      firstName:'',
      email:'',
      number:''
    }
  }
}
</script>

<style scoped>

</style>
