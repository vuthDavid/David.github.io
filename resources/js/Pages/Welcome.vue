<script setup>
import Frontend from '@/Layouts/Frontend.vue';
import { Head, Link } from '@inertiajs/vue3';
import FrontendLayout from '@/Layouts/Frontend.vue';
import Hero from '@/Components/Frontend/Hero.vue';
import Promote from '@/Components/Frontend/Promote.vue';
import Skills from '@/Components/Frontend/Skills.vue';
import About from "@/Components/Frontend/About.vue";
import portfolio from '@/Components/Frontend/portfolio.vue';
import Service from '@/Components/Frontend/Service.vue';
import ContanctMe from '@/Components/Frontend/ContanctMe.vue';


// defineProps({
//     canLogin: {
//         type: Boolean,
//     },
//     canRegister: {
//         type: Boolean,
//     },
//     laravelVersion: {
//         type: String,
//         required: true,
//     },
//     phpVersion: {
//         type: String,
//         required: true,
//     },
// });

// function handleImageError() {
//     document.getElementById('screenshot-container')?.classList.add('!hidden');
//     document.getElementById('docs-card')?.classList.add('!row-span-1');
//     document.getElementById('docs-card-content')?.classList.add('!flex-row');
//     document.getElementById('background')?.classList.add('!hidden');
// }
// defineProps({
//     skill:Object,
// });

defineProps({
    skills:Object,
    projects:Object,
});
</script>

<template>
    <Head title="Welcome to portfolio" />
    <!-- <Frontend></Frontend>    -->
     <FrontendLayout>
        <!-- Hero primary -->
         <Hero></Hero>
         <!-- Promote tail-100 -->
          <Promote></Promote>
          <!-- About secondary -->
            <about></about>
        <!-- skill primary -->
          <Skills :skills="skills" />
          <!-- portfolio  -->
           <portfolio :skills="skills" :projects="projects"/>
           <!-- service -->
            <Service></Service>
            <!-- ContantMe -->
             <ContanctMe/>

     </FrontendLayout>
    
</template>
