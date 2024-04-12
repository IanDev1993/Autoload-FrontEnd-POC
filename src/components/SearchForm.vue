<template>

<form action="" class="py-3 px-4 flex items-center">
    <label for="" class="sr-only">Search</label>
    <div class="relative w-full">
        <input type="text" @input="search" placeholder=" Search here..." class="bg-gray-50 border-gray-300 text-gray-900 text-lg">
    </div>
</form>

</template>
<script setup>
const emit = defineEmits(['search']);
const search = (e)=>{
   emit('search',e.target.value);
};


</script>