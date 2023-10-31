<template>
        <div class="items">
            <input 
                v-model="post.title"
                class="decorate" 
                type="text" 
                placeholder="имя" 
            >
            <input 
                v-model="post.subtitle" 
                class="decorate" 
                type="text" 
                placeholder="комментарий" 
            >
            <button 
                class="btn"
                @click="createPost"
            >
                добавить
            </button>
        </div>
</template>

<script>
    export default {
        data() {
            return {
                post: {
                    title: '',
                    subtitle: ''
                }
            }
        },
        methods: {
                createPost() {
                    this.post.id = Date.now();
                    this.$emit('create', this.post)
                    this.post = {
                        title: '',
                        subtitle: ''
                    }
                    // if (this.title.trim() !== '' && this.subtitle.trim() !== '') {
                    //     const newPost = {
                    //     id: Date.now(),
                    //     title: this.title,
                    //     subtitle: this.subtitle,
                    //     }
                    //     this.posts.push(newPost)
                    //     this.title = ''
                    //     this.subtitle = ''
                    // } else {
                    //     if (this.title.trim() === '') {
                    //         this.title = 'can not be empty'
                    //     } 
                    //     if (this.subtitle.trim() === '')
                    //         this.subtitle = 'can not be empty'
                    // }
            },
        }
    }
</script>

<style scoped>
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
</style>