<template>
    <div v-bind="divName">

    </div>
</template>
<script>
 
import player from '@vimeo/player';

    export default{
        data(){
            return{
                divName: 'divFrame'
            }
        },
        props:{
            id:{
                type:String
            }
        },
        created(){
            this.divName=this.divname +'_'+ this.id
        },  
        mounted(){
            let vm=this
            var options={
                id:this.id,
                Response:true
            }
             new player(this.divName,options);
        }
    }

</script>