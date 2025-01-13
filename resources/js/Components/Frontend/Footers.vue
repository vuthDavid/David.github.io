<script setup>
import {ref} from 'vue';
const showMobileMenu =ref('false');
</script>

<template> 

<footer class="bg-light-secondary  py-12">
          <div class="container mx-auto">
            <div class="
                    flex flex-col
                    md:flex-row
                    space-y-6
                    lg:space-y-0
                    items-center
                    justify-between
            ">
                <div class="flex space-x-6 items-center justify-center">
                    <img
                    class="h-11 w-auto"
                      src="logo.png"
                      alt="Logo David" />
                </div>
                <p class="text-paragraph opacity-80 text-[15px]">
                    &copy; 202 Laravel.com All right reserved.
                </p>
            </div>

          </div>
    </footer>

</template>
