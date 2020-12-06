<template>
    <div>
         
        <img class="card-img-top" v-bind:src="member.image" alt="">
        
        <div class="card-body">
            <h5 class="card-title text-center mb-0">{{ member.nombre }}</h5>
            <p class="card-text text-center"><small class="text-muted">{{ member.rol }}</small></p>

            <hr>

            <p class="card-text mb-1"><small class="text-muted"> Código 00{{ member.codigo }}</small></p>
            <p style="font-size: 13px;">{{ member.descripcion }}</p>

        </div>
 
    </div>
</template>

<script>

// import datos from "../assets/json/members.json";

export default {
    name: "TeamCard",
    props: ['member']
    // computed: {
    //     items() {
    //     return datos.map((item) => {
    //         return item;
    //     })
    //     }
    // }
}
</script>

<style scoped>
.team {
    background-color: #000127;
    display: flex;
    justify-content: space-between;
    text-align: center;
    margin-top: 10px;
    
}

.team-image{
    
    height: 220px;
    justify-content: space-between;
    align-items: center;
    /* margin: 50px 1px; */
    margin-top: 20px;
    margin-bottom: 100;
    padding : 0 20px;
    border-radius: 200px;
}

.team div{
    border-color: rgb(255, 255, 255);
    border-width: 100px;
}

.team h1{
    color: white;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    /* font-weight: 500; */

}

.team h4{
    color: gray;
    font-weight: 200;
}
</style>