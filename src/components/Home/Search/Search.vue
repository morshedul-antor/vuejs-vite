<script setup>
import { ref, watchEffect } from 'vue'

// import { useRoute } from 'vue-router'
// const route = useRoute()
// route.params.id

const users = ref([])
const search = ref()
const isLoading = ref(false)

const fetchData = async (id) => {
    isLoading.value = true

    try {
        const response = await fetch(`https://jsonplaceholder.typicode.com/users?id=${id}`)
        const data = await response.json()

        if (response.ok) {
            console.log('user:', data)
            users.value = data
            isLoading.value = false
        }
    } catch (err) {
        console.log(err.message)
    }
}

watchEffect(() => {
    if (search.value) {
        fetchData(search.value)
    }
})
</script>

<template>
    <div>
        <p>User:</p>
        <input type="number" v-model="search" placeholder="enter user id" />

        <p v-if="isLoading">Loading...</p>
        <p v-else v-for="(user, index) in users" :key="index">
            {{ user.name }} ({{ user.username }})
        </p>
    </div>
</template>
