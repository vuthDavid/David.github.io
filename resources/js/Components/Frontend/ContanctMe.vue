<script setup>
import {ref} from 'vue';
import {useForm} from '@inertiajs/inertia-vue3';

const showMessage = ref (false);

const form=useForm({
    name:"",
    email:"",
    body:""
})
function setShowMessage(value) {
      showMessage.value = value;
    }
function cleanForm() {
    // Reset the form
    form.reset();
    // Show the message
    setShowMessage(true); 
    // Hide the message after 20 seconds
    setTimeout(() => {
        setShowMessage(false);
    }, 20000);
}

const submit = () =>{
    form.post(route("contact"),{
        preserveScroll: true,
        onSuccess: () => cleanForm(),
        onError: (errors) => {
            // Handle validation errors
            console.error("Form submission errors:", errors);
            // You can also set error messages in the UI if needed
        },
        onFinish: () => {
            // This can be used to reset loading state or any final actions
            console.log("Form submission finished");
        }

    });

}
</script>

<template>
    <section id="contact" class="section bg-accent-default-100 dark:bg-dark-secondary">
        <div class="container mx-auto"
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
                <div class="flex flex-col items-center text-center">
                    <h2 class="section-title items-center text-center">
                        Contant Me
                    </h2>
                    <p class="subtitle">
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Eius impedit obcaecati consequatur doloribus animi quibusdam. Veniam necessitatibus eum, asperiores est eligendi nesciunt modi eaque cumque, magnam molestias placeat, quae incidunt.

                    </p>
                </div>
                <div class="flex flex-col lg:flex-row lg:gap-x-8">
                    <div class="flex flex-1 flex-col
                                items-start
                                space-y-8
                                mb-12
                                lg:mb-0
                                lg:pt-2
                            ">
                            <div class="flex flex-col lg:flex-row lg:gap-x-4">                                
                            <div
                             class=" text-accent-default 
                                            rounded-sm
                                            w-14
                                            h-14
                                            flex
                                            items-start
                                            justify-center
                                            mt-2
                                            lg:mb-0
                                            text-2xl
                                ">
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
                                 <path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 0 1-2.25 2.25h-15a2.25 2.25 0 0 1-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0 0 19.5 4.5h-15a2.25 2.25 0 0 0-2.25 2.25m19.5 0v.243a2.25 2.25 0 0 1-1.07 1.916l-7.5 4.615a2.25 2.25 0 0 1-2.36 0L3.32 8.91a2.25 2.25 0 0 1-1.07-1.916V6.75" />
                                </svg>

                            </div>
                            <div>
                                <h4 class="font-body text-xl mb-1">Have a question</h4>
                                <p class="mb-1 text-paragraph">I am hero to help you.</p>
                                <p class="text-accent-default font-normal">Email me at david.com</p>
                            </div>        
                         </div>
                         <div class="flex flex-col lg:flex-row lg:gap-x-4">                                
                            <div
                             class=" text-accent-default 
                                            rounded-sm
                                            w-14
                                            h-14
                                            flex
                                            items-start
                                            justify-center
                                            mt-2
                                            lg:mb-0
                                            text-2xl
                                ">
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M15 10.5a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z" />
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1 1 15 0Z" />
                                </svg>


                            </div>
                            <div>
                                <h4 class="font-body text-xl mb-1">Current Location</h4>
                                <p class="mb-1 text-paragraph">Pnom Phneh</p>
                                <p class="text-accent-default font-normal">Serving Client</p>
                            </div>   
                         </div>
                  </div>
                 <form @submit.prevent="submit" class="space-y-8 w-full max-w-md">
                    <div
                        v-if="showMessage"
                     class="m-2 p-4 bg-light-tail-500 dark:bg-dark-navy-100 text-light-secondary rounded-lg">
                        Thank you for Contanting me.
                    </div>
                    <div class="flex gap-8">
                        <div>
                             <input v-model="form.name" type="text" class="input" placeholder="Your Name" required /> 
                            <span v-if="form.errors.name" class="text-sm m-2 text-red-400">{{ form.errors.name }}</span> 
                        </div>
                        <div>
                            <input v-model="form.email" type="text" class="input" placeholder="Your Email" required> 
                            <span v-if="form.errors.email" class="text-sm m-2 text-red-400">{{form.errors.email}}</span>                      
                        </div>                        
                    </div>
                    <textarea v-model="form.body" class="textarea" placeholder="Your Message" spellcheck="false" required></textarea>
                    <span v-if="form.errors.body" class="text-sm m-2 text-red-400">{{ form.errors.body }}</span> 
                    <!-- <button @click="setShowMessage"  class="btn btn-lg bg-accent-default hover:bg-secondary">Send Message</button> -->
                    <button @click="setShowMessage"
                            class="group inline-block rounded bg-gradient-to-r from-pink-500 via-red-500 to-yellow-500 p-[2px] hover:text-white focus:outline-none focus:ring active:text-opacity-75"
                            href="#"
                        >
                            <span class="block rounded-sm bg-white px-8 py-3 text-sm font-medium group-hover:bg-transparent">
                            Send Message
                            </span>
                        </button>
                </form>
            </div>
        </div>
    </section>
</template>