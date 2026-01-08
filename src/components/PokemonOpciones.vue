<template>
    <div class="opciones-container">
        <ul>
            <li>Pokemon 1</li>
            <li>Pokemon 2</li>
            <li>Pokemon 3</li>
            <li>Pokemon 4</li>
        </ul>

    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
    ul{
        list-style-type: none;
    }
    li{
        background-color: white;
        border-radius: 5px ;
        border: solid 1px black;
        cursor: pointer;
        margin-top: 5px;
        width: 200px;
        font-size: 30px;
        text-align: center;
    }
    .opciones-container{
        display: flex;
        justify-content: center;
        
    }
</style>