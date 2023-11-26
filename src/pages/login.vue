<script setup lang="ts">
import { ref } from 'vue'
import { useRouter } from 'vue-router'
import { useAuthStore } from '@/stores/auth'

const auth = useAuthStore()
const username = ref('')
const password = ref('')
const router = useRouter()

const onLogin = () => {
    auth.login(username.value, password.value)

    router.push('/')
}
</script>

<template>
    <div>
       <h1>Login Page</h1>
       <div class="flex flex-col gap-2">
           
            <input type="text" v-model="username" class="border p-2" placeholder="tulis username"/>
            <input type="number" v-model="password" class="border p-2" placeholder="tulis pass angka"/>
            <button @click="onLogin()" class="bg-green-700 text-white py-2 px-4">Login</button>
        </div>
    </div>
</template>