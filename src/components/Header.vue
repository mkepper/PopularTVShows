<template>
    <div class="header">
        <h1>{{theTitle}}</h1>
    </div>
</template>

<script>
export default {
    name: "Header",
    props: ['theTitle']
}
</script>

<style scoped>
.header{
    background: white;
    color: black;
    text-align: center;
    padding: 10px;
    margin: 0px;
}

</style>