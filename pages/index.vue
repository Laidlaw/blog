<template>
  <div >
    <section class="hero is-info is-fullheight">
      <div class="hero-body">
        <div class="container">
          <figure class="avatar image is-128x128 is-centered is-clipped">
            <img :src="person.fields.image.fields.file.url" />
          </figure>
          <h1 class="title is-1">
            {{ person.fields.name }}
          </h1>
          <h2 class="subtitle is-4">
            {{ person.fields.title }}
          </h2>
          <article>{{ person.fields.shortBio }}</article>
        </div>
      </div>
    </section>
    <section class="hero is-light is-medium">
      <div class="items-bar wrapper">
        <h1 class="is-success title">Recent articles</h1>
      </div>
      <div class="container is-fluid">
        <div class="content">
          <div class="columns">
            <div class="column" v-for="post in posts">
              <article-preview :post="post"></article-preview>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import {createClient} from '~/plugins/contentful.js'
import ArticlePreview from '~/components/article-preview.vue'

const client = createClient()

export default {
  asyncData ({env}) {
    return Promise.all([
      client.getEntries({
        'sys.id': env.CTF_PERSON_ID
      }),
      client.getEntries({
        'content_type': env.CTF_BLOG_POST_TYPE_ID,
        order: '-sys.createdAt'
      })
    ]).then(([entries, posts]) => {
      return {
        person: entries.items[0],
        posts: posts.items
      }
    }).catch(console.error)
  },
  components: {
    ArticlePreview
  }
}
</script>

<style>

.avatar {
  overflow: hidden;
  border-radius: 50%;
  margin-bottom: 5vh;
}
/*.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}*/

/*
.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
/*  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}
*/

/*
.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}*/
</style>
