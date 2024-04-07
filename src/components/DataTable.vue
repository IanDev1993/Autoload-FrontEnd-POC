<script setup>
defineProps({
    items: {
        type: Array,
        required: true
    }
})
</script>

<template>
    <table>
        <tr v-for="item in items" :key="item.id">        
            <td>{{ item.code }}</td>
            <td>{{ item.createdAt }}</td>
            <td>{{ item.status }}</td>
        </tr>
    </table>
</template>