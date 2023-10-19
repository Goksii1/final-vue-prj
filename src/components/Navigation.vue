<template>
    <div class="container">
        <nav>
            <router-link to="/">Регистрация</router-link>
            <router-link to="/chat">Чат</router-link>
            <router-link to="/test">Команды NBA</router-link>

        </nav>
    </div>
</template>

<script>
    export default{
        name:"NavComp",
    }
</script>

<style scoped>
    .container{
        background-color: #D3D3D3;
        height: 70px;
        display: flex;
        justify-content: center;
        border-radius: 30px;
        width: 100%;
       
    }
    nav{
        width: 500px;
        height: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 30px;
        text-decoration: none;
        
    }
</style>