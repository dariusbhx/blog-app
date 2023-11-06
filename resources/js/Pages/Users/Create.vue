<template>
    <Head title="Create User" />

    <h1>Create New User</h1>

    <form @submit.prevent="submit" class="max-w-md mx-auto mt-8">
        <div class="mb-6">
            <label class="block mb-2 uppercase font-bold text-xs text-gray-700" for="name">
                Name
            </label>

            <input
                class="border border-gray-400 pr-2 w-full"
                type="text"
                name="name"
                id="name"
                v-model="form.name"
                required
            >
        </div>
        <div class="mb-6">
            <label class="block mb-2 uppercase font-bold text-xs text-gray-700" for="name">
                Email
            </label>

            <input
                class="border border-gray-400 pr-2 w-full"
                type="email"
                name="email"
                id="email"
                v-model="form.email"
                required
            >
        </div>

        <div class="mb-6">
            <label class="block mb-2 uppercase font-bold text-xs text-gray-700" for="name">
                Password
            </label>

            <input
                class="border border-gray-400 pr-2 w-full"
                type="password"
                name="password"
                id="password"
                v-model="form.password"
                required
            >
        </div>

        <div class="mb-6">
            <button type="submit" class="bg-blue-400 text-white rounded py-2 px-4 hover:bg-blue-500">
                Submit
            </button>
        </div>
    </form>
</template>

<script setup>
    import {Head} from '@inertiajs/vue3'
    import {Inertia} from "@inertiajs/inertia";

    let form = {
        name: '',
        email: '',
        password: ''
    }

    let submit = () => {
        Inertia.post('/users', form);
    }
</script>
