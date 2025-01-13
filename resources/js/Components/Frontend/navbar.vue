<script setup>
import { Link } from '@inertiajs/vue3';
import {ref,onMounted} from 'vue';
const showMobileMenu =ref('false');
const ScrollBg =ref(false);
const navigetions= [
  {name: 'Home', href:'#home'},
  {name: 'About', href:'#about'},
  {name: 'Portfolio', href:'#portfolio'},
  {name: "Service" , href: "#service"},
  {name: "Contact" , href: "#contact"},
 {
  name: "Login",
   href: "/login"
}

]
const setScrollBg=(value)=>{
      ScrollBg.value=value;
}

onMounted(()=>{
  window.addEventListener("scroll",()=>{
    return window.scrollY >50  ?setScrollBg(true) :setScrollBg(false);
  })
})

</script>

<template> 
<nav class="
     w-full
      fixed
      z-20    
       border-gray-200       
        px-2
        sm:px-4
        py-2.2
        "
        :class="{
              'bg-light-secondary  dark:bg-gray-900' : ScrollBg , 
              'bg-white dark:bg-slate-800' : !ScrollBg}"
        >
  <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
    <a href="#" class="flex items-center space-x-3 rtl:space-x-reverse">
        <img  
        src="logo.png"        
         class="h-14  "  alt=" Logo" />
        <span class="self-center text-2xl font-semibold whitespace-nowrap dark:text-white">Portfolio</span>
    </a>
    <button @click="showMobileMenu = ! showMobileMenu" data-collapse-toggle="navbar-default" type="button" class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600" aria-controls="navbar-default" aria-expanded="false">
        <span class="sr-only">Open main menu</span>
        <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h15M1 7h15M1 13h15"/>
        </svg>
    </button>
    <div class=" w-full md:block md:w-auto" :class="{hidden : showMobileMenu}"  id="navbar-default">
      <ul class="font-semibold
       flex flex-col
        p-4 md:p-0 mt-4         
          rounded-lg        
           md:flex-row
           md:space-x-8 rtl:space-x-reverse 
           md:mt-0    
           
        ">
        <li v-for="(navigetions , index) in navigetions" :key="index">
          <a :href="navigetions.href" 
          class="block py-2 px-3  rounded md:bg-transparent md:text-light-tail-500 hover:dark:text-light-secondary md:p-0 dark:text-light-tail-500 hover:text-dark-navy-500" aria-current="page">
            {{ navigetions.name }}
          </a>
          
        </li>
        
      </ul>
    </div>
  </div>
</nav>

</template>
