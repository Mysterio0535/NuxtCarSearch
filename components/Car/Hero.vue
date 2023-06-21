
<template>
    <!-- IMAGE CAR -->
    <div 
    class="relative h-screen w-100 bg-no-repeat bg-cover bg-bottom 
    bg-[url('https://images.wallpaperscraft.ru/image/single/ferrari_458_mm_speciale_110967_3840x2400.jpg')]">
      <!-- CONTENT -->
     <div class="z-10 absolute w-full h-full flex justify-center items-center">
       <div class="text-center w-1/2">
         <h1 class="text-8xl font-serif text-white mb-10">Find your drive</h1>
         
         <CarSearchBar/>
         
       </div>
     </div>
     <!-- dark background -->
     <div class="z-1 absolute w-full h-full bg-black opacity-50"></div>
   </div>
</template>