<template>
    <Head title="Skills index" />
   <AuthenticatedLayout>
       <template #header>
           <h2 class="text-xl font-semibold leading-tight text-gray-800">
               Edit Project
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
                <InputError class="mt-2" :message="$page.props.errors.skill_id"/> 

            </div>
          <div>
            <InputLabel for="name" value="name"/>
            <TextInput type="text" name="name" id="name" class="mt-1 block w-full" required
            v-model="form.name"                   
                   />  
            <InputError class="mt-2" :message="$page.props.errors.name"/> 
          </div>
          <div class="mt-2">
            <InputLabel for="project_url" value="URL"/>
            <TextInput id="project_url" type="text" v-model="form.project_url" class="mt-1 block w-full"

            />
            <InputError class="mt-2" :message="$page.props.errors.project_url"/> 
          </div>
        <div class="mt-2">
            <InputLabel for="Image" value="Image"/>

            <TextInput id="image" type="file" @input="form.image=$event.target.files[0]" class="mt-1 block w-full"

            />
            <InputError class="mt-2" :message="$page.props.errors.image"/> 
            <div class=" w-20 h-20 rounded-sm mt-5 bg-slate-400">
              <img :src="form.image" alt="Image" />
            </div>
        </div>  
          <div class="mt-4 flex items-center justify-end ">        
                <PrimaryButton class="ms-4">                  
                   Update
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
import  {Inertia}  from "@inertiajs/inertia";

const props= defineProps({
    skills:Array,
    project:Object

})
const form = useForm({
    name: props.project?.name,
    image: props.project ? `storage/projects/${props.project.image}` : null,
    skill_id: props.project?.skill_id,
    project_url: props.project?.project_url
   
});

const submit = () => {
    Inertia.post(`/projects/${props.project.id}`,{
      _method: "put",
      name: form.name,
      image: form.image,
      skill_id: form.skill_id,
      project_url: form.project_url

    })
       
    
};
</script>

<style >

</style>