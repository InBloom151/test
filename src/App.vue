<template>
    <div class="app">
        <post-form @create="createPost"></post-form>
        <post-list :posts="posts" @remove="removePost"></post-list>
    </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
export default {
    components: {
        PostForm, PostList
    },
    data() {
        return {
            posts: [
                {id: 0, title: 1, text: 1},
                {id: 1, title: 2, text: 2},
                {id: 2, title: 3, text: 3},
            ],
        }
    },
    methods: {
        createPost(post) {
            this.posts.push(post);
        },
        removePost(post) {
            this.posts = this.posts.filter(p => p.id !== post.id);
        },
    }
}
</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.app {
    padding: 20px;
}
</style>