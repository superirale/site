<template>
   <div>
    <Header />
    <div class="container">
      <div class="posts">
          <div class="post" v-for="article of articles" :key="article.slug">
              <h1> <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">{{article.title}}</NuxtLink></h1>
              <div class="post-date"><i class="fa fa-custom fa-clock-o"></i> <span>{{ article.createdAt}}</span></div>

              <p>
                {{ article.description }}
              </p>
            <hr>
          </div>
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
      const articles = await $content('articles')
        .only(['title', 'description', 'img', 'slug', 'author', 'createdAt'])
        .sortBy('createdAt', 'asc')
        .fetch()

      return {
        articles
      }
    },
    head() {
        return {
            title: "Blog ",
            meta: [{
                hid: 'description',
                name: 'description',
                content: 'Articles'
            }],
        } 
    },
}
</script>
