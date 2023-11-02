<template>
    <div class="all">
        <PostForm 
            @create="createPost"
        />
        <Posts 
            :posts="posts"
            @onPostRemove="removePost"
        />
    </div>
</template>

<script>
    import PostForm from './components/PostForm.vue';
    import Posts from './components/Posts.vue';

    export default {
        components: {
            PostForm,
            Posts,
},
        data() {
            return {
                posts: [],
            }
        }, 
        methods: {
            createPost(post) {
                this.posts.push(post);
            },
            removePost(index) {
                this.posts.splice(index, 1)
            }
        }
    }

</script>

<style>
    .all {
        display: flex;
        flex-direction: column;
        gap: 50px;
    }
</style>