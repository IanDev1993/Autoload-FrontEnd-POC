<script setup>
import { ref, computed } from 'vue';
import SearchForm from './SearchForm.vue';
import FilterDropDown from './FilterDropDown.vue';
import FilterRadios from './FilterRadios.vue';

const searchFilter = ref('');

const props = defineProps({
    items: {
        type: Array,
        required: true
    }
});

const filterdItems = computed(()=>{
    if(searchFilter.value != '')
        return props.items.filter(item => item.code.includes(searchFilter.value))  
    else
        return props.items;
});
const handleSearch = (search)=>{
    searchFilter.value = search;
};
</script>

<template>
    <div class="bg-white relative border rounded-lg">
        <div class="flex items-center justify-between">
            <SearchForm @search="handleSearch" />             
                <div class="flex items-center justify-end text-sm font-semibold ">
                    <FilterRadios />                                
                    <FilterDropDown />
                </div>   
        </div>
        <table class="w-full text-sm text-left text-gray-500">
            <thead class="text-lg text-gray-700  bg-gray-100">
                <tr>
                    <th class="px-4 py-3">Code</th>
                    <th class="px-4 py-3">Create At</th>
                    <th class="px-4 py-3">Status</th>          
                    <th class="px-4 py-3">
                        <span class="sr-only">Actions</span>
                    </th>
                </tr>
    
            </thead>
            <tbody>
                <tr v-for="item in filterdItems" :key="item.id" class="border-b">        
                    <td class="px-4 py-3 font-medium text-gray-900">{{ item.code }}</td>
                    <td class="px-4 py-3">{{ item.createdAt }}</td>
                    <td class="px-4 py-3">{{ item.status }}</td>            
                    <td class="px-4 py-3 flex items-center justify-end">
                     <a href="#" v-show="!item.status" class="text-indigo-500 hover:underline">Validate</a>
                    </td>
                </tr>                    
            </tbody>
        </table>
    </div>
</template>