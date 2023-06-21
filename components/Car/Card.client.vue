<script setup>
import heartRed from "@/assets/heartRed.png";
import heartBlack from "@/assets/heartBlack.png";

const props = defineProps({
  car: Object,
  favored: Boolean
})

const emit = defineEmits(['favor'])


// const favored = useState(`favored-${props.car.id}`, () => {
//   return false
// })

</script>

<template>
    <div class="relative shadow border w-full overflow-hidden mb-5 cursor-pointer h-[200px]"
    >
    
    <img class="absolute w-7 right-5 top-2 z-20" 
    :src="favored ? heartBlack : heartRed"
    @click="$emit('favor', car.id)"/>
    
    <div class="flex h-full" @click="navigateTo(`/car/${car.name}-${car.id}`)">

           <NuxtImg 
           :src="car.url" 
           :alt="car.name"
           class="w-[300px] h-full"/>

           <div class="p-4 flex flex-col">
             <div>
               <h1 class="text-2xl text-blue-700">{{ car.name }}</h1>
               <p class="text-gray-700">{{ car.description }}</p>
             </div>
             <h1 class="mt-auto text-xl">{{ car.price }} $</h1>
           </div>
         </div>
      </div>
</template>