<template>
<div>
     <h1>Hall of Fame</h1>
    <div v-for="hf in hall_fame" v-bind:key="hf._id">
        <ul>
            <li>Player Name : {{hf.player_name}} 
            <li>Amount Won : {{hf.fund}}</li>      
        </ul>
    </div>
</div>
    
</template>

<script>
import axios from 'axios';
export default {
    created : async function(){
        let response = await axios.get('https://3000-a88bcf79-3e7e-45cd-813f-c8573ee6fa79.ws-us03.gitpod.io/');
        this.hall_fame = response.data;
    },
    data : function(){
        return{
            'hall_fame' : []
        }
    } 
    
}
</script>

<style scoped>
h1{
    text-align: center;
}

ul{
      text-align: center;
}

</style>