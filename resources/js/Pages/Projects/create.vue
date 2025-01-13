<template>
    <Head title="Skills index" />
   <AuthenticatedLayout>
       <template #header>
           <h2 class="text-xl font-semibold leading-tight text-gray-800">
               New Project
           </h2>
       </template>

    <div class="py-12">
      <div class="mx-auto max-w-md sm:px-6 lg:px-8 bg-white">
        <form class="p-4" @submit.prevent="submit">
            <div>
                <InputLabel for="skill" value="skill"/>
                <select v-model="form.skill_id" id="skill_id" name="skill_id" 
                class="mt-1 block w-full pl-3 pr-10 py-2 text-base border-gray-300 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm rounded-md">
                    <option v-for="skill in skills" :key="skill.id" :value="skill.id">{{skill.name}}</option>
                </select>
            </div>
          <div>
            <InputLabel for="name" value="name"/>
            <TextInput type="text" name="name" id="name" class="mt-1 block w-full" required
            v-model="form.name"                   
                   />  
            <InputError class="mt-2" :message="form.errors.name"/> 
            
          </div>
          <div class="mt-2">
            <InputLabel for="project_url" value="URL"/>
            <TextInput id="project_url" type="text" v-model="form.project_url" class="mt-1 block w-full"

            />
            <InputError class="mt-2" :message="form.errors.project_url"/> 
          </div>
        <div class="mt-2">
            <InputLabel for="Image" value="Image"/>
            <TextInput @change="Getimage" id="image" type="file" @input="form.image=$event.target.files[0]"
             class="mt-1 block w-full"
            />
            <div class=" w-20 h-20 rounded-sm mt-5 bg-slate-400">
              <img :src="show" alt="">
            </div>

           
            
        </div>  
          <div class="mt-4 flex items-center justify-end ">        
                <PrimaryButton class="ms-4">                  
                   Store
                </PrimaryButton>
            </div>
        </form>
      </div>
    </div>
   </AuthenticatedLayout>
 
</template>

<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head, useForm } from "@inertiajs/vue3";
import InputError from "@/Components/InputError.vue";
import InputLabel from "@/Components/InputLabel.vue";
import PrimaryButton from "@/Components/PrimaryButton.vue";
import TextInput from "@/Components/TextInput.vue";

defineProps({
    skills:Array
})
const form = useForm({
    name: '',
    image: '',
    skill_id: '',
    project_url:''
   
});

const submit = () => {
    form.post(route('projects.store'));
       
    
};

</script>
<script>
    export default {
      data(){
        return{
          show: null
        }

      },

      methods:{
        Getimage(e){
         let image = e.target.files[0];
         let reader = new FileReader();
         reader.readAsDataURL(image);
         reader.onload = e =>{
            this.show = e.target.result
         }
        }
      },
      components: {
        InputError,
    },
    data() {
        return {
            form: {
                errors: {
                    name: '' // Initialize error messages
                }
            }
        };
    }
    }
</script>


<style >

</style>