<template>
    <div class="card">
        <div class="cards" v-for="card in cardList" v-bind:key="card.id">
            <img v-bind:src="'https://image.tmdb.org/t/p/w300//' + card.poster_path" />
            <h3>{{card.name}}</h3>
            <p>{{card.overview}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: "Card",
    props: ['theTitle','cardList']
}
</script>

<style scoped>
.card{
    display: table;
    background: white;
    color: black;
    text-align: center;
    padding: 10px;
    margin: auto;
    
}

.cards{
    width: 300px;
    height: 700px;
    float: left;
    border: gray;
    border-style: solid;
    border-width: 3px;
}

p{
    padding: 10px;
}

</style>