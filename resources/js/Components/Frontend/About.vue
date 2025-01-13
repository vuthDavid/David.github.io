<template>
    <section id="about" class="section bg-light-seccondary">
        <div class="container mx-auto"
         v-motion
            :initial="{
                opacity:0,
                y:100,
            }"    
            :visible="{
                opacity:1,
                y:0,
            }">
            <div class="flex flex-col xl:flex-row gap-24">
                <img
                class="object-cover h-full w-[566px] md:mx-auto lg:mx-0 rounded-2xl"
                src="picture.jpg" 
                 alt="about">
                <div class="flex flex-col items-center text-center lg:items-start lg:text-left">
                    <div class="flex flex-col">
                        <h2 class="text-3xl lg:text-4xl font-medium lg:font-extrabold mb-3">
                            About me
                        </h2>
                        <p class="mb-4 text-accent-default">
                            Freelance Backend web developer
                        </p>
                        <hr class="mb-8 opacity-100 dark:opacity-5">
                        <p class="mb-8">
                            I am a person who likes to learn new things, be calm, share knowledge, and like to help others. <br/>
                        </p>
                    </div>
                    
                    <a
                    class="group relative inline-block overflow-hidden border border-accent-default px-8 py-3 focus:outline-none focus:ring"
                    href="#"
                >
                    <span
                    class="absolute inset-y-0 left-0 w-[2px] bg-accent-default transition-all group-hover:w-full group-active:bg-indigo-500"
                    ></span>
                
                    <span
                    class="relative text-sm font-medium text-indigo-600 transition-colors group-hover:text-white"
                    >
                    Contact me
                    </span>
                </a>

                </div>
            </div>

            <div class=" w-50 h-2/6 mt-20  ">
                <div class=" flex items-center justify-center space-x-3 ">
                    <a href="https://t.me/VuthDavid9999" class="inline-block rounded-xl bg-indigo-600 px-8 py-3 text-sm font-medium text-white transition hover:scale-110 hover:shadow-xl focus:outline-none focus:ring active:bg-indigo-500"
                    
                    target="_blank">Telegram</a>

                    <a href="https://web.facebook.com/profile.php?id=100071473570320"
                    class="inline-block rounded-xl bg-indigo-600 px-8 py-3 text-sm font-medium text-white transition hover:scale-110 hover:shadow-xl focus:outline-none focus:ring active:bg-indigo-500"
                      >facebook</a>
                    
                </div> 
            </div>
            <div class="flex flex-col xl:flex-row gap-20 mt-10 items-center justify-center ">
                        <img
                        class="object-cover h-full w-[466px] md:mx-auto lg:mx-0 rounded-2xl hover:scale-110 transition border-blue-500 "
                        src="image.png" 
                        alt="about">

                        <img
                class="object-cover h-full w-[466px] md:mx-auto lg:mx-0 rounded-2xl  hover:scale-110 transition"
                src="photoCertiv.jpg" 
                 alt="about">

                 <img
                class="object-cover h-full w-[466px] md:mx-auto lg:mx-0 rounded-2xl  hover:scale-110 transition"
                src="learn.jpg" 
                 alt="about">
            </div>
        </div>


        
    </section>
</template>