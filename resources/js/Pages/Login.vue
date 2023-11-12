<template>
 <main class="grid place-items-center min-h-screen">
     <section class="bg-white p-8 rounded-xl max-w-md mx-auto border">
         <Head title="Create User" />

         <h1 class="text-3xl mb-6 ">Login</h1>

         <form @submit.prevent="submit">
             <div class="mb-6">
                 <label class="block mb-2 uppercase font-bold text-xs text-gray-700" for="name">
                     Email
                 </label>

                 <input
                     class="border  pr-2 w-full"
                     type="email"
                     name="email"
                     id="email"
                     v-model="form.email"
                     required
                 >

                 <div v-if="form.errors.email" v-text="form.errors.email" class="text-red-500 text-sm"></div>
             </div>

             <div class="mb-6">
                 <label class="block mb-2 uppercase font-bold text-xs text-gray-700" for="name">
                     Password
                 </label>

                 <input
                     class="border pr-2 w-full"
                     type="password"
                     name="password"
                     id="password"
                     v-model="form.password"
                     required
                 >
                 <div v-if="form.errors.password" v-text="form.errors.password" class="text-red-500 text-sm"></div>

             </div>

             <div class="mb-6">
                 <button type="submit" class="bg-blue-400 text-white rounded py-2 px-4 hover:bg-blue-500" :disabled="form.processing">
                     Log In
                 </button>
             </div>
         </form>
     </section>
 </main>
</template>

<script>
import {Head} from '@inertiajs/vue3';
export default {
    layout:null,
}
</script>

<script setup>
import {useForm} from "@inertiajs/vue3";

let form = useForm({
    email:'',
    password: ''
});

let submit = () => {
    form.post('/login', form);
}
</script>
