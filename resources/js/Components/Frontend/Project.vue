<script setup>

import Projects from "./Projects.vue";
import {ref} from "vue"



const props = defineProps({
    skills:Object,
    projects:Object,
});
const filterProjects =ref(props.projects.data);
const SeleledId=ref('all');
const filtered= (id) =>{
    if(id === "all"){
        filterProjects.value=props.projects.data
        SeleledId.value=id;
    }else{
        filterProjects.value=props.projects.data.filter(project => {
            return project.skill.id ===id;
        });
        SeleledId.value=id;
    }
}
</script>
<template>
    <div class="container mx-auto dark:bg-dark-navy-500">
        <nav class="mb-12 border-b-2 border-light-tail-500 dark:border-light-secondary dark:text-dark-navy-100">
            <ul class="flex flex-col lg:flex-row justify-evenly items-center">
                <li class="cursor-pointer capitalize m-3">
                    <button 
                    @click="filtered('all')"
                    class=" flex text-center px-4 py-2 hover:bg-light-tail-100 bg-accent-default dark:bg-accent-default rounded-lg
                    text-light-secondary hover:text-light-secondary dark:text-dark-navy-100"
                     :class="[SeleledId === 'all' ? '' : 'bg-light-tail-100 dark:bg-light-tail-100']"
                     >
                        All
                    </button>                    
                </li>
                <li class=" cursor-pointer capitalize m-4 hover:bg-accent-default bg-light-tail-100 dark:bg-light-tail-100 rounded-lg" v-for="projectSkill in skills.data" :key="projectSkill.id">
                    <button 
                    @click="filtered(projectSkill.id)"
                    class=" hover:scale-90 transition flex text-center px-4 py-2 hover:text-light-tail-500 dark:text-dark-navy-100" 
                    :class="[SeleledId == projectSkill.id ? 'bg-accent-default  text-light-secondary dark:text-light-secondary rounded' : ''] "> 
                    {{ projectSkill.name }}
                    </button>
                </li>
            </ul>

        </nav>
        <section class="grid gap-y-12 lg:grid-cols-3 lg:gap-8 ">
            <Projects v-for="project in filterProjects"
             :key="project.id" :project="project" />
        </section>

    </div>
</template>