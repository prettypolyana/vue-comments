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
            <MyButton 
                class="btn"
                @click="createPost"
            >
                добавить
            </MyButton>
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
                    if (this.post.title !== '' && this.post.subtitle !== '') {
                        this.post.id = Date.now();
                        this.$emit('create', this.post)
                        this.post = {
                            title: '',
                            subtitle: ''
                        };
                    } else {
                        if (this.post.title === '') {
                            this.post.title = 'can not be empty';
                        } 
                        if (this.post.subtitle === '') {
                            this.post.subtitle = 'can not be empty';
                        }
                    }
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
        width: 800px;
        margin: auto;
    }
</style>