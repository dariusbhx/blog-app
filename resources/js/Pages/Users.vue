<template>
    <h1 class="text-3xl">Users </h1>

    <div style="margin-top:700px;">
        <p>The current time is {{ time }}</p>

        <Link href="/users" class="text-blue-500" preserve-scroll >refresh</Link>
    </div>
</template>
    
<script setup>
 
    defineProps({
        time: String
    });
</script>    