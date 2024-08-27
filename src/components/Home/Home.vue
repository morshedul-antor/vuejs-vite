<script setup>
import classes from './Home.module.css'
import Counter from './Counter/Counter.vue'
import Fetch from './Fetch/Fetch.vue'
import Search from './Search/Search.vue'

// Define the props
defineProps({
    msg: String
})
</script>

<!-- Home Component -->
<template>
    <div :class="classes.home">
        <h1>Vue.js</h1>
        <h3>{{ msg }}</h3>

        <Counter />
        <!-- <Fetch /> -->
        <Search />
    </div>
</template>
