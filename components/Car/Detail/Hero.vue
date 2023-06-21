<script setup>
const props = defineProps({
  car: Object
})
</script>


<template>
    <!-- <div class="mx-auto mt-4 max-w-7xl space-y-4 px-4 xs:px-8 sm:px-10 lg:px-16 pb-16 w-3/5 "> -->
   <div class="mt-10">
    
     <NuxtImg class="w-full" :src="car.url"/>
     <h1 class="mt-10 text-4xl">{{ car.name }}</h1>

     <div class="text-slate-500 flex text-lg mt-3 border-b pb-5 justify-between">
       <div class="flex">
         <p class="mr-2 ">{{ car.seats }} seats</p>
         <p class="mr-2 ">|</p>
         <p class="mr-2 ">{{ car.miles }} mile</p>
       </div>
       <div>
         <p class="font-bold text-2xl">${{ car.price }}</p>
       </div>
     </div>

   </div>
   <!-- </div> -->
</template>