<template>
        <div class="posts" v-for="post in posts">
            <div class="post"> Имя: {{post.title}} </div>
            <div class="post"> Комментарий: {{post.subtitle}} </div>
        </div>
</template>

<script>
    export default {
        props: {
            posts: {
                type: Array,
                required: true,
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
        width: 100%;
        height: 90px;
        padding: 10px;
        border: 2px solid rgb(26, 209, 81);
    }

    .post {
        border: 1px solid rgb(116, 116, 209);
        height: 40px;
    }
</style>