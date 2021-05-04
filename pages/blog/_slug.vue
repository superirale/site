<template>
    <div>
        <Header />
        <div class="container">
        <div class="blog-post">
            <div class="post-header">
                <h1>{{article.title}}</h1>
                <div class="post-date">
                    <i class="fa fa-custom fa-clock-o"></i>
                    <span> Published on: {{article.createdAt}}</span>
                </div>
            </div>
            <div class="post-body">
                <nuxt-content :document="article" />
                <hr>
            </div>
            <p class="social-share">
                Please share, if you find this article helpful.
                <br><br>

                <a class="twitter-share-button"
                href="https://twitter.com/intent/tweet?text=Introduction to Flask"
                data-size="large"><script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
                Tweet</a>
            </p>
        </div>
        </div>
    </div>

</template>
<script>
    export default {
        data () {
            return {
            }
        },
        
        async asyncData({ $content, params }) {
            const article = await $content('articles', params.slug).fetch()
         
            return { article }
        },
        methods : {
            formatDate() {

            }
        }
    }
</script>