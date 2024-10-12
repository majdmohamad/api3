<template>
    <div class="our-blog">
        <h1>{{ pageName }}</h1>
        <p>{{ pageDescription }}</p>
        <div class="container">
            <div class="row">
                <div class="col-md-8">
                    <div class="posts-area">
                        <BlogPosts
                            v-for="post in posts"
                            v-bind:key="post.id"
                            :viewe="post.viewe"
                            :title="post.title"
                            :content="post.content"
                            :author="post.author"
                            :category="post.category"
                        />
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="sidebar">
                        <h2>New post</h2>
                        <form @submit.prevent="submitPost">
                            <label for="title">Title:</label>
                            <input
                                type="text"
                                v-model="newPost.title"
                                required
                            />
                            <hr />

                            <label for="content">Content:</label>
                            <textarea
                                v-model="newPost.content"
                                required
                            ></textarea>
                            <hr />

                            <label for="viewe">viewe:</label>
                            <input
                                type="text"
                                v-model="newPost.viewe"
                                required
                            />
                            <hr />

                            <label for="author">Author:</label>
                            <input
                                type="text"
                                v-model="newPost.author"
                                required
                            />
                            <hr />

                            <label for="category">Category:</label>
                            <input
                                type="text"
                                v-model="newPost.category"
                                required
                            />
                            <hr />

                            <button type="submit">Submit</button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import BlogPosts from "@/components/BlogPosts.vue";
import axios from "axios";
export default {
    data: function () {
        return {
            pageName: "Blog",
            pageDescription: "This Is Blog Page",
            posts: [],
            newPost: {
                title: "",
                content: "",
                author: "",
                category: "",
            },
        };
    },
    name: "blogMy",
    components: {
        BlogPosts,
    },
    methods: {
        fetchPosts() {
            axios
                .get("https://apidjango2-1.onrender.com/api/posts/")
                .then((response) => {
                    this.posts = response.data;
                })
                .catch((error) => {
                    console.error("Error fetching posts:", error);
                });
        },
        submitPost() {
            axios
                .post(
                    "https://apidjango2-1.onrender.com/api/posts/",
                    this.newPost
                )
                .then((response) => {
                    this.posts.push(response.data); // إضافة البوست الجديد إلى القائمة
                    this.newPost = {
                        title: "",
                        content: "",
                        author: "",
                        category: "",
                        date: "",
                    }; // إعادة تعيين النموذج
                })
                .catch((error) => {
                    console.error("Error posting:", error);
                });
        },
    },
    mounted() {
        this.fetchPosts();
    },
};
</script>

<style lang="scss" scoped>
.sidebar {
    padding: 40px;
    height: 800px;
    background-color: #fff;
    box-shadow: 0 0 10px #ddd;

    input {
        margin: 10px;
        width: 65%;
    }

    textarea {
        margin: 10px;
        width: 65%;
    }

    button {
        margin: 20px;
    }
}
</style>
