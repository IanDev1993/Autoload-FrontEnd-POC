<script setup>
import DataTable from './components/DataTable.vue';

import {ref, onMounted} from "vue";

const items = ref([]);

onMounted( async () => {
   const response = await fetch('http://localhost:5008/order');
   items.value = await response.json(); 
});
</script>


<template>
 <div class="p-8 bg-gray-400 min-h-screen">
    <DataTable :items="items"/>
 </div>
</template>
