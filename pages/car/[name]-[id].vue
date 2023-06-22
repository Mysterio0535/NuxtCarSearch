<script setup>
// import useFetchCar from '~/composables/useFetchCar';

const route = useRoute()
const {cars} = useCars()

// const {data, car} = await useFetchCar(route.params.id)
const user = useSupabaseUser()

const {toTitleCase} = useUtilities()

useHead({
title: toTitleCase(route.params.name)
})

const car = computed(() => {
    return cars.find((c) => {
        return c.id === parseInt(route.params.id)
    })
})

if(!car.value) {
    throw createError({
        statusCode: 404,
        message: `Car with id of ${route.params.id} does not exist`
    })
}

definePageMeta({
    layout: "custom"
});

</script>

<template>
    
    <!-- чтобы не делать отдельные импорты 
        по компонентах мы можем присвоить 
        каждому компоненту нужный елемент обтекта -->

    <div>
        <!-- <div class="mx-auto mt-4 max-w-7xl space-y-4 px-4 xs:px-8 sm:px-10 lg:px-16 pb-16 w-3/5 "> -->
            <CarDetailHero :car="car" />
            <CarDetailAttributes :features="car.features"/>
            <CarDetailDescription :description="car.description"/>
            <CarDetailContact/>
        <!-- </div> -->
    </div>
</template>