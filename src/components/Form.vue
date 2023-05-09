<template>
    <form @submit.prevent>
        <input type="text" name="text" v-model="post.text">
        <button @click="createPost">Отправить</button>
    </form>
</template>
<script>
    export default{
        data(){
            return {
                post: {
                    text: '',
                    status: false
                }
            }
        },
        methods: {
            createPost(){
                this.post.id = Date.now()
                this.$emit('create', this.post)
                console.log(this.post)
                this.post = {
                    text: ''
                }
            }
        }   
    }
</script>
<style>
    form{
        border: 1px solid white;
        padding: 10px;
        display: flex;
        flex-direction: column;
        gap: 20px;
        width: 100%;
        margin: 20px auto;
    }
    button{
        background: rgb(32, 147, 32);
        color: white;
        padding: 10px 20px;
        width: 100%;
        border: none;
    }
    input{
        width: 100%;
        background: none;
        border: 1px solid rgb(32, 147, 32);
        padding: 10px 20px;
        color: white;
        outline: none;
    }
</style>