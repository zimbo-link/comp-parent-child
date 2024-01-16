<template>
    <div style="border:1px solid black; margin: 10px;">
        <h1>Parent Component</h1>
        <div>Bool: <span>{{bool}}</span></div>
        <div>Text: <span>{{text}}</span></div>
        <child-component
            v-on:toggle-bool="toggleBool" 
            v-on:change-text="changeText"
            />
    </div>
</template>

<script setup>
import { ref } from 'vue';
import ChildComponent from './child-component';

const bool = ref(false); 
const text = ref('');

const toggleBool = () => {
    bool.value = !bool.value
}

const changeText = (val) => {
    text.value = val
}
</script>