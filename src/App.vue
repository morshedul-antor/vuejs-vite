<script>
import { createRouter, createWebHistory } from 'vue-router'
import { Home, About } from './components'

// Define your routes
const routes = [
    { path: '/', component: Home, props: { msg: 'Hello from router!' } },
    { path: '/about', component: About }
]

// Create the router instance
const router = createRouter({
    history: createWebHistory(),
    routes
})

export default {
    name: 'App',
    router
}
</script>

<!-- App -->
<template>
    <router-view></router-view>
</template>
