<script setup>
import { ref, onMounted } from 'vue'

const users = ref([])
const fetchData = async () => {
    try {
        const response = await fetch('https://jsonplaceholder.typicode.com/users')
        const data = await response.json()

        if (response.ok) {
            console.log('users:', data)
            users.value = data
        }
    } catch (err) {
        console.log(err.message)
    }
}

onMounted(fetchData)
</script>

<!-- Fetch -->
<template>
    <div>
        <p v-for="(user, index) in users" :key="index">
            {{ index + 1 }}. {{ user.name }} ({{ user.username }})
        </p>
    </div>
</template>
