<template>
  <main class="post individual">
    <h1>{{ post.title.rendered }}</h1>
    <small class="date">{{ post.date | dateformat }}</small>
    <section v-html="post.content.rendered"></section>
  </main>
</template>

<script>
export default {
  data() {
    return {
      slug: this.$route.params.slug,
    }
  },
  computed: {
    posts() {
      return this.$store.state.posts
    },
    post() {
      return this.posts.find((el) => el.slug === this.slug)
    },
  },
  created() {
    this.$store.dispatch('getPosts')
  },
}
</script>

<style lang="scss" scoped>
main.post {
  margin: 0px auto 50px;
  max-width: 800px;
  padding: 30px 70px;
  background: $white;
}

h1 {
  color: black;
  font-size: 40px;
}

section {
  color: #444;
}

.date {
  text-align: center;
}
</style>
