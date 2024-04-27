
<script setup>

    const emit = defineEmits(['search']);

    const search = (e)=>{

     emit('search',e.target.value);

    };

</script>

<template>
    <form class="py-3 px-4 flex items-center">    
        <div class="relative w-full">
            <input type="search" @input="search" placeholder="Search code..." class="py-1 px-2 bg-gray-100 border-gray-200 text-gray-900 text-lg caret-red-500" />
        </div>
    </form>
</template>
