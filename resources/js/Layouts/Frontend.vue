<script setup>

import navbar from "@/Components/Frontend/navbar.vue";
import Footers from "@/Components/Frontend/Footers.vue";

import Skills from "@/Components/Frontend/Skills.vue";
  components: { navbar,Footers }
  
  </script>
<template>
    <div class="bg-slate-200 dark:bg-slate-900">
        <!-- Header -->        
           <navbar></navbar>
        
        <main class="min-h-screen">            
            <slot />
         </main>
         <!-- About -->
         <!-- <About></About> -->
         <!-- Footer -->
          <!-- skill -->

        
         <Footers></Footers>
      
         
    </div>
</template>