<script setup>
import { ref, defineEmits } from 'vue';
import ParentComponent from './ParentComponent.vue';

const emit = defineEmits(['messageEmitted'])
const displayMessage = ref('Message from the Parent Component')

function sendMessage() {
    displayMessage.value = 'Message from Child Component on clicked'
    return displayMessage.value;
}

</script>

<template>
    <div class="text-red-500">
    <ParentComponent :message="displayMessage"/>
    </div>
<button @click="$emit('messageEmitted', sendMessage())" class="mt-6 hover:bg-rose-500 font-bold bg-rose-200">Update Message</button>

</template>

<style scoped>

</style>