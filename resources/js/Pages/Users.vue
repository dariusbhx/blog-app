<template>
    <Head title="Settings" />
    <h1 class="text-3xl">Users </h1>

    <ul>
        <li
            v-for="user in users"
            :key="user.id"
            v-text="user.name"
        >
        </li>
    </ul>

</template>

<script setup>
import {Head} from '@inertiajs/vue3'

defineProps({
    users: Array
});
</script>
