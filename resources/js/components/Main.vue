<template>
    <main>
        <div class="cards">
            <div v-for="(post, index) in posts" :key="index" class="card">
                <img v-bind:src="post.image" />
                <h4>{{ post.title }}</h4>
                <p>{{ post.content }}</p>
            </div>
        </div>
    </main>
</template>
<script>
export default {
    name: "Main",
    data() {
        return {
            posts: [],
        };
    },

    created() {
        axios.get("/api/posts").then((response) => {
            this.posts = response.data;
        });
    },
};
</script>

<style></style>
