<template>
    <Head>
        <title>My App - Users</title>
    </Head>
    <h1 class="text-3xl">Users </h1>

    <div style="margin-top:700px;">
        <p>The current time is {{ time }}</p>

        <Link href="/users" class="text-blue-500" preserve-scroll>refresh</Link>
    </div>
</template>

<script setup>
import {Head} from '@inertiajs/vue3'

defineProps({
    time: String
});
</script>
