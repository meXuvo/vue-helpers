<template>
  <div class="w-2/5 bg-white shadow rounded-md group">
    <div class="px-5 py-5 mb-3">
        <div class="flex justify-between space-x-5">
        <div class="2/5 mt-2">
            <div class="bg-red-100 px-2 py-2 rounded-full">
                <span class="text-red-600">
                    <com-icon name="alert" svgStyleClasses="w-6 h-6 transform group-hover:scale-110 fill-current" />
                </span>
            </div>
        </div>
        <div class="flex-1 mt-2">
            <div class="w-full flex justify-between items-center">
                <div>
                    <p class="text-lg font-bold text-gray-800 tracking-wide ">Delete now</p>
                </div>
                <!-- close -->
                <div>
                    <span @click="closeModal" class="text-gray-700 select-none cursor-pointer">
                        <com-icon name="close" svgStyleClasses="w-6 h-6 fill-current"/>
                    </span>
                </div>
            </div>
        </div>
    </div>
    <div class="ml-16">
        <p class="text-sm tracking-wide leading-relaxed text-gray-700">Are you sure you want to delete this? The data will be removed on our servers.</p>
    </div>
    </div>
    <div class="px-5 py-3 flex justify-end ">
        <div class="space-x-2">
            <!-- cancel -->
            <button @click="closeModal" class="text-sm font-medium tracking-wider px-5 py-2 rounded border-2 border-gray-200 text-gray-800 focus:outline-none ">Cancel</button>
            <!-- Delete -->
            <button @click="dataDelete(id)" class=" text-sm font-medium tracking-wider px-5 py-2 rounded bg-red-600 text-white focus:outline-none shadow hover:bg-red-700">Delete</button>
        </div>
    </div>
  </div>
</template>

<script>
import ComIcon from '../Shared/ComIcon.vue'
export default {
  components: { ComIcon },
  props:['id'],
  methods:{ 
      dataDelete(id){
          alert(`Delete data ${id}`)
          this.closeModal()
      },
      closeModal(){
          this.$emit('closeModal')
      }
  },
}
</script>

<style>

</style>