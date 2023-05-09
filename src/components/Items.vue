<template>
    <div class="items">
        <div class="item" v-for="post in posts">
            <h1>{{ post.id }}</h1>
            <p>{{ post.text }}</p>      
            <input class="checkbox" type="checkbox">
            <button @click="this.$emit('remove', post)">УДАЛИТЬ</button>
        </div>
    </div>
</template>
<script>
    export default{
        props: {
            posts: {
                type: Array,
                required: true
            }
        }
    }
</script>
<style>
    .items{
        padding: 10px;
        margin: 10px;
        display: flex;
        flex-direction: column;
        gap: 20px;
    }
    .checkbox{
        width: 20px;
    }
    .item h1{
        font-size: 30px;
        border-right: 1px solid black;
        padding: 10px;
    }
    .item{
        display: flex;
        justify-content: space-between;
        gap: 20px;
        align-items: center;
        padding: 20px;
        background: white;
        color: #000;
    }
</style>