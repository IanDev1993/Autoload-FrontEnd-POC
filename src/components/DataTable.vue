<script setup>
defineProps({
    items: {
        type: Array,
        required: true
    }
})
</script>

<template>
    <div class="bg-white relative border rounded-lg">
        <table class="w-full text-sm text-left text-gray-500">
            <thead class="text-xs text-gray-700 uppercase bg-gray-50">
                <tr>
                    <th class="px-4 py-3">Code</th>
                    <th class="px-4 py-3">CreateAt</th>
                    <th class="px-4 py-3">Status</th>
                    <th class="px-4 py-3">ID</th>
                    <th class="px-4 py-3">
                        <span class="sr-only">Actions</span>
                    </th>
                </tr>
    
            </thead>
            <tbody>
                <tr v-for="item in items" :key="item.id" class="border-b">        
                    <td class="px-4 py-3 font-medium text-gray-900">{{ item.code }}</td>
                    <td class="px-4 py-3">{{ item.createdAt }}</td>
                    <td class="px-4 py-3">{{ item.status }}</td>
                    <td class="px-4 py-3 font-medium text-gray-900">{{ item.id }}</td>
                    <td class="px-4 py-3 flex items-center justify-end">
                     <a href="#" class="text-indigo-500 hover:underline">Details</a>
                    </td>
                </tr>                    
            </tbody>
        </table>
    </div>
</template>