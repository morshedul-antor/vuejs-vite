<script setup>
import { ref } from 'vue'

const count = ref(0)
const increment = () => {
    count.value++
}
</script>

<!-- Counter -->
<template>
    <div>
        <p>{{ count }}</p>
        <button @click="increment">Increment</button>
    </div>
</template>
