<template>
    <div class="container">
             <li class="game" > {{ nome }}</li>
    </div>
</template>

<script>
export default {
    name: 'MeuGameFavorito',
    props: {
        nome: {
            type: String,
        }
    }
}

</script>

<style scoped>

.game {
    list-style: none;
    padding: 12px;
    margin: 5px;
    background-color: #7289da;
    color: #ffffff;
    border: 1px solid #c0c0c0;
    font-size: 16px;
    border-radius: 3px;
}

.game:hover{
    border: 1px solid #ffffff;

}
</style>