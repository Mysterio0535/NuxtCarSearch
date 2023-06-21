<script setup>
const city = ref("");
const cityError = ref(false)

// Изменяем путь по тому что заполнил пользователь
const handleSearch = () => {
    if(!city.value) {
        return cityError.value = true
    }
    navigateTo(`/city/${city.value}/car`)
}

</script>

<template>
    <!-- SEARCH BAR -->
    <div
        class="font-serif w-[1000px] text-2xl rounded-full bg-white flex justify-between overflow-hidden drop-shadow-2xl mx-auto">
        <input 
        type="text" 
        class="py-3 px-5 w-full twxt-2xl rounded-full focus:outline-none"
        :class="cityError ? 'bg-red-500' : ''"
        placeholder="Search Your Car By City..."
        v-model="city">
        <button class="bg-sky-500 px-10 text-white" @click="handleSearch">
            Search
        </button>
    </div>
</template>