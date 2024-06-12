<template>
<div>
    <div class="blog-post-holder col-10" v-if="post">
        <div class="blog-post">
            <h1>{{ post.title }}</h1>
            <img :src="blogImage" alt="Post image">
            <hr>
            <div v-html="post.content" class="blog-content"></div>
        </div>
    </div>
</div>
</template>

<script>
import posts from '@/blog/posts.json';

export default {
    data() {
        return {
            postId: this.$route.params.id,
        };
    },
    computed: {
        post() {
            return posts.posts.find((post) => post.id == this.postId);
            //this is a lifecycle hook that runs when the component is created
        },
        blogImage() {
            return require(`@/assets/images/${this.post.image}`);
        },
    },
    mounted() {
        //NOTES ON THIS WRITE DOWN WHAT THIS DOES AND HOW IT WORKS NEXT WEEK
        // FINISH YOUR BLOG POST ABOUT DOCKER AND VUE.JS
        document.title = this.post.title;
        let metaDescription = document.querySelector('meta[name="description"]');
        if (metaDescription) {
            metaDescription.setAttribute('content', this.post.excerpt);
        } else {
            let meta = document.createElement('meta');
            meta.name = "description";
            meta.content = this.post.description;
            document.getElementsByTagName('head')[0].appendChild(meta);
        }

        let metaKeywords = document.querySelector('meta[name="keywords"]');
        if (metaKeywords) {
            metaKeywords.setAttribute('content', this.post.tags.join(', '));
        } else {
            let meta = document.createElement('meta');
            meta.name = "keywords";
            meta.content = this.post.tags.join(',');
            document.getElementsByTagName('head')[0].appendChild(meta);
        }
    },
};
</script>
<style>
img {
    width: 500px;
    height: 500px;
}
.blog-post{
    margin: 10px;
    padding: 10px;
    display: block;
    background: var(--main-white-color);
    border: #171616 2px solid;
    border-radius: 10px;
    }
.blog-content {
    align-items: start;
    text-wrap: wrap;
    color: var(--main-text-color);
    font-size: 1.2rem;
    font-weight: 400;
    line-height: 1.5;
}
pre {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: left;
    white-space: pre-wrap;
}
.blog-post-holder {
    margin: auto;
    padding: 10px;
    display: block;
    justify-content: space-between;
    align-items: start;
    background: var(--main-white-color);
    border: #171616 2px solid;
} 

</style>;
