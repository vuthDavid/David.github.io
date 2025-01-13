<template>
  <Head title="Skills index" />
  <AuthenticatedLayout>
    <template #header>
      <h2 class="text-xl font-semibold leading-tight text-gray-800">
        New Skill
      </h2>
    </template>

    <div class="py-12">
      <div class="mx-auto max-w-md sm:px-6 lg:px-8 bg-white">
        <form class="p-4" @submit.prevent="submit">
          <div>
            <InputLabel for="name" value="name"/>
            <TextInput type="text" name="name" id="name" class="mt-1 block w-full" required
            v-model="form.name"                   
                   />  
                   <InputError class="mt-2" :message="$page.props.errors.name"/> 
          </div>
          <div class="mt-2">
            <InputLabel for="Image" value="Image"/>

            <TextInput id="image" type="file" @input="form.image=$event.target.files[0]" class="mt-1 block w-full"

            />
            <InputError class="mt-2" :message="$page.props.errors.image"/>
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


const form = useForm({
    name: '',
    image: '',
   
});

const submit = () => {
    form.post(route('skills.store'));
       
    
};
</script>

<style >
</style>