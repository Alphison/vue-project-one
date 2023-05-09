<template>
    <div id="app">
        <Form @create="createPost"/>
        <Items :posts="posts" @remove="removePost"/>
    </div>
</template>
<script>
    import Form from "@/components/Form.vue"
    import Items from "@/components/Items.vue"
    export default {
        components: {
            Form,
            Items
        },
        data(){
            return {
                posts: [
                    {
                        id: 1,
                        text: 'loremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremlorem',
                        status: false
                    },
                    {
                        id: 2,
                        text: 'loremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremlorem',
                        status: false
                    },
                    {
                        id: 3,
                        text: 'loremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremloremlorem',
                        status: false
                    }
                ],
            }
        },
        methods: {
            createPost(post){
                // console.log(post)
                this.posts.push(post)
            },
            removePost(post){
                this.posts = this.posts.filter(p => p.id !== post.id)
            }
        }
    }
</script>
<style>
    *{
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    #app{
        
    }
    body{
        background: #000;
        color: white;
    }
</style>