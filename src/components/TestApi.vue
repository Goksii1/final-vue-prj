<template>
    <div class="container">
        <div class="title">КOМАНДЫ</div>
        <div v-if="isLoad" class="loading">Загрузка данных...</div>
        <div v-else class="data">
            <div v-for="(el, i) in teamData" :key="el.id">
                {{ i + 1 }} . {{ el.addreviation }} {{el.city}}
                <img src="https://cdn-icons-png.flaticon.com/512/1483/1483063.png" alt=""
                style="width: 15px; height: 15px;" @click="removeTeam(el.id)">

            </div>
        </div>
    </div>
    

</template>

<script>
    export default {
        name: 'TestApi',
        data() {
            return{
                teamData: [],
                isLoad: true
            };
        },
        mounted(){
            const url = 'https://free-nba.p.rapidapi.com/teams?page=0'
            const options = {
                method: "GET",
                headers:{
                    "X-RapidAPI-key": "488f437511msh2d3854838388c55p13692cjsn135921cfebdf",
                    "X-RapidAPI-Host": "free-nba.p.rapidapi.com",
                },
            };
            fetch(url, options)
            .then((res)=> res.json())
            .then((res)=>{
                this.teamData = res.data;
                this.isLoad = false;
            });
        },

        methods:{
            removeTeam(id){
                this.teamData = this.teamData.filter((el) => el.id !== id);


            }

        }


    }
</script>
<style scoped>
    .container{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    .title{
        font-size: 2em;
        color: black;
        margin: 10px;
        font-weight: bold;
    }
    .data{
        padding: 20px;
    }
    .loading{
        padding-bottom: 20px;
    }
    img{
        cursor: pointer;
        margin-left: 10px;
    }
    
</style>