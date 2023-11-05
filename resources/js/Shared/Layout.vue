<template>
    <Head>
        <title>My App</title>
        <meta type="description" content="Information about my app" head-key="description">
    </Head>
    <section class="p-6 bg-gray-200">
        <header class="flex justify-between">
            <h1 class="font-bold text-lg">
                My App
            </h1>
            <Nav/>
        </header>
        <p>Welcome Back {{ $page.props.auth.user.username }}</p>
    </section>

    <section class="p-6">
        <div class="max-w-3xl mx-auto">
            <slot/>
        </div>
    </section>
</template>

<script setup>
import Nav from "./Nav.vue";
import {Head} from '@inertiajs/vue3'
</script>
