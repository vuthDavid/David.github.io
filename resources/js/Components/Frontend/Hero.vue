<script setup>
</script>
<template>
    <section id="home" class="lg:h-[85vh] flex items-center  py-32 lg:py-0 overflow-hidden">
        <div class="container mx-auto h-full"
        v-motion
            :initial="{
                opacity:0,
                y:100,
            }"    
            :visible="{
                opacity:1,
                y:0,
            }"
        >
            <div class="flex flex-col md:flex-row items-center h-full pt-8">
                <div class="flex-1 flex flex-col items-center lg:items-start">
                    <p class="text-lg text-md mb-[22px]">Welcome to My Portfolio</p>
                    <h1 class="text-4xl leading-[44px] md:text-5xl md:leading-tight lg:text-7xl lg:leading-[1.2] font-bold md:tracking-[-2px] bg-gradient-to-r from-blue-600 via-green-500 to-indigo-400 inline-block text-transparent bg-clip-text">
                        I Web Developer & Designer
                    </h1>
                    <p class="pt-4 pb-8 md:pb-12 max-w-[480px] text-lg text-center lg:text-left">
                       Hi, this is David ❤️ . I'm a developer and  designer. Beside coding, I can Video Editor.
                    </p>
                    <!-- <button class="btn btn-md bg-accent-default hover:bg-light-primary  dark:hover:bg-dark-secondary dark:hover:text-dark-navy-100 md:btn-lg transition-all">
                        Work with me
                    </button> -->
                        <button 
                            class="group inline-block rounded bg-gradient-to-r from-pink-500 via-red-500 to-yellow-500 p-[2px] hover:text-white focus:outline-none focus:ring active:text-opacity-75"
                            href="#"
                        >
                            <span class="block rounded-sm bg-white px-8 py-3 text-sm font-medium group-hover:bg-transparent">
                            Work with me
                            </span>
                        </button>
                    
                </div>
               <div class="flex lg:flex flex-1 justify-end items-center h-full mt-8 md:mt-2 space-x-3">
                    <img class=" rounded-full h-90 w-80 border-double border-4 border-sky-500"
                     src="profiledavid1.jpg" 
                     alt="Hero">                    

                    <div class="bg-white font-semibold w-60 ml-3">
                        <h2 class="  font-semibold  bg-gradient-to-r from-purple-500 to-pink-500">Vuth David</h2>
                        <h3 class="ml-3 text-slate-900">neatvid9999@gmail.com</h3>
                        <h4 class="ml-3 text-slate-900">099 216296</h4>
                    </div>
               </div>
                       
               
            </div>
              <article>
                         
                    
                        
                </article>

            

        </div>
    </section>
</template>