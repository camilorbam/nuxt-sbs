<template>
  <div>
    <div class="posts">
      <main>
        <div>
          <h1 class="page-title icon-doc">Sports Betting Blog</h1>
          <p>
            <img
              class="alignright size-full wp-image-1722"
              src="https://sbstg.wpengine.com/wp-content/uploads/2016/09/blog_page.png"
              alt="SBS News"
              width="210"
              height="110"
            />The sports betting blog section of
            <a href="https://sbstg.wpengine.com/"
              ><strong>Safest Betting Sites</strong></a
            >
            covers everything from sports betting advice to musings on the
            latest in the sporting and gambling world. Our blog aims to give the
            most up to date information on betting (which is an excellent
            complement our extensive library of sports betting content) while
            mixing in some humor. Head over to our
            <a
              href="https://sbstg.wpengine.com/picks/"
              target="_blank"
              rel="noopener noreferrer"
              >free picks section </a
            >for our latest free picks on a variety of sports.
          </p>
        </div>
        <div v-for="post in sortedPosts" :key="post.id" class="post">
          <h3>
            <a :href="`blog/${post.slug}`">{{ post.title.rendered }}</a>
          </h3>
          <small>{{ post.date | dateformat }}</small>
          <div v-html="post.excerpt.rendered"></div>
          <a :href="`blog/${post.slug}`" class="readmore slide">Read more ⟶</a>
        </div>
      </main>
      <aside>
        <h2 class="tags-title">Tags</h2>
        <div class="tags-list">
          <ul>
            <li
              v-for="tag in tags"
              :key="tag.id"
              :class="[tag.id === selectedTag ? activeClass : '']"
              @click="updateTag(tag)"
            >
              <a>{{ tag.name }}</a>
              <span v-if="tag.id === selectedTag">✕</span>
            </li>
          </ul>
        </div>
      </aside>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedTag: null,
      activeClass: 'active',
    }
  },
  computed: {
    posts() {
      return this.$store.state.posts
    },
    tags() {
      return this.$store.state.tags
    },
    sortedPosts() {
      if (!this.selectedTag) return this.posts
      return this.posts.filter((el) => el.tags.includes(this.selectedTag))
    },
  },
  created() {
    this.$store.dispatch('getPosts')
  },
  methods: {
    updateTag(tag) {
      if (!this.selectedTag) {
        this.selectedTag = tag.id
      } else {
        this.selectedTag = null
      }
    },
  },
}
</script>

<style lang="scss">
h1 {
  line-height: 1.2em;
}
.page-title {
  position: relative;
  margin-bottom: 20px;
  padding: 10px 0 10px 80px;
  color: #ffffff;
  background: url('/h1-heading-bg.jpeg') #34495e no-repeat;
  font-family: 'Roboto Condensed', Arial Narrow, Arial, sans-serif;
  font-size: 25px;
}

.posts {
  display: grid;
  grid-template-columns: 2fr 1fr;
  grid-template-rows: 1fr;
  grid-column-gap: 6vw;
  margin: 0px auto 5em;
  max-width: 80vw;
  padding: 25px 20px;
  background: #ffffff;
}

main {
  grid-area: 1 / 1 / 2 / 2;
}

aside {
  grid-area: 1 / 2 / 2 / 3;
}

a,
a:active,
a:visited {
  color: #2980b9;
  text-decoration: underline;
}

a.readmore {
  display: inline-block;
  font-size: 11px;
  text-transform: uppercase;
  padding: 5px 15px;
  letter-spacing: 2px;
  position: relative;
  color: #000;
  font-weight: 700;
  font-family: 'Open Sans', serif;
  border: 1px solid #ccc;
  background: #fff;
}

.tags-title {
  position: relative;
  margin: 0px;
  padding: 10px 10px 10px 38px;
  color: #ccdceb;
  background-color: #34495e;
  font-family: 'Open Sans', Helvetica Neue, Helvetica, Arial, sans-serif;
  font-size: 15px;
}

.tags-list {
  background: #f5f5f5;
  padding: 25px 25px;
}

.post {
  border-bottom: 1px solid rgb(223, 222, 222);
  margin-bottom: 2em;
  padding-bottom: 2em;
  color: #444;

  h3 {
    margin-bottom: 0.5em;
    font-size: 26px;
  }
}

.tags-list ul {
  padding-left: 0;
}

.tags-list li {
  font-family: 'Open Sans', serif;
  letter-spacing: 1px;
  text-transform: uppercase;
  padding: 6px 15px;
  margin: 0 0 10px 10px;
  display: inline-block;
  font-size: 0.7rem !important;
  border: 1px solid #000;
  transition: all 0.3s;
  outline: none;
  font-weight: normal;
  cursor: pointer;
  background: #fff;
  a {
    color: #000;
  }
}

.active {
  border: 1px solid #d44119;
  background-color: #fae091 !important;
}

.slide {
  position: relative;
  background: transparent;
  -webkit-transition: 0.3s ease;
  transition: 0.3s ease;
  z-index: 1;
  backface-visibility: hidden;
  perspective: 1000px;
  transform: translateZ(0);
  cursor: pointer;

  &:hover {
    color: #fff;
  }

  &:hover:before {
    right: -1px;
  }
}
</style>
