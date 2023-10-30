<template>
    <div class="all">
        <div class="items">
            <input v-bind:value="title" class="decorate" type="text" placeholder="имя" @input="title = $event.target.value">
            <input v-bind:value="subtitle" class="decorate" type="text" placeholder="комментарий" @input="subtitle = $event.target.value">
            <button  @click="createPost" class="btn">добавить</button>
        </div>
        <div class="posts" v-for="post in posts">
            <div class="post"> Имя: {{post.title}} </div>
            <div class="post"> Комментарий: {{post.subtitle}} </div>
        </div>
    </div>
</template>

<script>

    export default {
        data() {
            return {
                title: '',
                subtitle: '',
                posts: [],
                full: false,
            }
        }, 
        methods: {
            createPost() {
                if (this.title.trim() !== '' && this.subtitle.trim() !== '') {
                    const newPost = {
                    id: Date.now(),
                    title: this.title,
                    subtitle: this.subtitle,
                    }
                    this.posts.push(newPost)
                    this.title = ''
                    this.subtitle = ''
                } else {
                    if (this.title.trim() === '') {
                        this.title = 'can not be empty'
                    } 
                    
                    if (this.subtitle.trim() === '')
                        this.subtitle = 'can not be empty'
                }
            },
        }
    }

</script>

<style>
    .all {
        display: flex;
        flex-direction: column;
        gap: 50px;
    }

    .decorate {
        height: 40px;
        border: 2px solid rgb(116, 116, 209);
    }

    .items {
        display: flex;
        flex-direction: column;
        gap: 15px;
    }

    .btn {
        width: 100px;
        align-self: flex-end;
        height: 30px;
        background-color: aliceblue;
        border: 2px solid rgb(116, 116, 209);

    }

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