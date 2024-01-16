<template>
    <div style="border:1px solid black; margin: 10px;">
        <h3>Child Component </h3>
        <div>
            <button @click="toggleBool">change bool</button>
        </div>
        <div>
            <p>
                <input v-on:keyup="changeText($event.target.value)" type="text" name="display" value="">
            </p>
        </div>
    </div>
</template>

<script setup>
import { defineEmits } from 'vue'

const emit = defineEmits(['toggle-bool', 'change-text'])

const toggleBool = () => {
    emit('toggle-bool');
}

const changeText = (val) => {
    emit('change-text', val);
}
</script>