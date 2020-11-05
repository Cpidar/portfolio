<template>
  <div>
    <banner-showcase />
    <banner-about />
    <!-- <banner-category :items="categories" /> -->
    <items-grid
      :title="title"
      :items="items"
    />
    <!-- <blog-grid :posts="posts" /> -->
    <!-- <banner-about :items="about" /> -->
    <!-- <banner-contactme /> -->
  </div>
</template>

<script>
import BannerShowcase from "~/components/banner-showcase.vue";
import ItemsGrid from "~/components/items-grid.vue";
import Contactme from "~/components/banner-contactme.vue";
import BannerCategory from "~/components/banner-category.vue";
import BannerAbout from "~/components/banner-about.vue";
import BlogGrid from "~/components/blog-grid.vue";
import BannerContactme from "~/components/banner-contactme.vue";

export default {
  components: {
    BannerShowcase,
    ItemsGrid,
    Contactme,
    BannerCategory,
    BlogGrid,
    BannerContactme,
  },
  async asyncData({ $content }) {
    const { title } = await $content('hello').only(['title']).fetch()
    const items = await $content('items').fetch()
    return {
      title,
      items
    };
  },
  methods: {
    async showMore(page) {},
  },
};
</script>

<style>
/* .container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
} */
</style>
