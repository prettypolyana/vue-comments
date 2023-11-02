<template>
        <div class="posts" v-for="post, index in posts">
            <div class="post"> Имя: {{post.title}} </div>
            <div class="post"> Комментарий: {{post.subtitle}} </div>
            <my-button @click="removePost(index)">delete</my-button>
        </div>
</template>

<script>
    export default {
        props: {
            posts: {
                type: Array,
                required: true,
            }
        },
        methods: {
            removePost(index) {
                this.$emit("onPostRemove", index)
            }
        }
    }
</script>

<style scoped>
    .posts {
        display: flex;
        justify-content: center;
        flex-direction: column;
        gap: 10px;
        width: 800px;
        height: 90px;
        padding: 10px;
        border: 2px solid rgb(26, 209, 81);
        margin: auto;
    }

    .post {
        border: 1px solid rgb(116, 116, 209);
        height: 40px;
    }
</style>