<template>
    <form @submit.prevent>
        <h4>Добавление поста</h4>
        <my-input v-model="post.title" class="input" type="text" placeholder="Название"></my-input>
        <my-input v-model="post.text" type="text" placeholder="Текст"></my-input>
        <my-button @click="createPost" style="align-self: flex-end; margin-top: 15px;">Добавить</my-button>
    </form>
</template>

<script>
export default {
    data() {
        return {
            post: {
                title: '',
                text: ''
            }
        }
    },
    methods: {
        createPost() {
            this.post.id = Date.now();
            this.$emit('create', this.post)
            this.post = {
                title: '',
                text: ''
            }
        },
    }
}
</script>

<style scoped>
form {
    display: flex;
    flex-direction: column;
}
</style>