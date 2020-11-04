<template>
  <div class="uk-section-muted uk-section-large">
    <div class="uk-position-relative">
      <div class="uk-margin-medium uk-container">
        <div class="tm-grid-expand uk-child-width-1-1 uk-grid uk-grid-stack" uk-grid>
          <div class="uk-width-1-1@m uk-first-column">
            <h2
              class="uk-position-relative uk-width-2xlarge uk-margin-auto uk-text-center"
              style="z-index: 1;"
            >
              <a href="/themes/wordpress/2020/kitchen-daily/index.php?post_type=recipe">120 recipes</a>
              everyone can make. Browse through
              <a
                href="/themes/wordpress/2020/kitchen-daily/index.php?page_id=52"
              >all categories</a> and pick your favorite dish for every occasion.
            </h2>
            <div
              class="uk-position-relative uk-margin-xlarge uk-margin-remove-bottom uk-text-center"
              style="z-index: 1;"
            >
              <div
                class="uk-child-width-auto uk-flex-center uk-grid-small uk-grid-match uk-grid"
                uk-grid
              >
                <div v-for="item in items" :key="item.id">
                  <a
                    class="el-item uk-panel uk-margin-remove-first-child uk-transition-toggle uk-link-toggle uk-display-block"
                    :href="'/'+item.name"
                  >
                    <div class="uk-cover-container uk-inline-clip uk-border-rounded" style="width:140px; height:93px;">
                      <img
                        :src="baseImagePath+item.image.formats.thumbnail.url"
                        :srcset="baseImagePath+item.image.formats.thumbnail.url"
                        sizes="(min-width: 140px) 140px"
                        width="140px"
                        height="93px"
                        class="uk-transition-scale-up uk-transition-opaque uk-position-cover"
                        alt
                        uk-cover
                      />
                    </div>

                    <div
                      class="el-title uk-h6 uk-margin-small-top uk-margin-remove-bottom"
                    >{{item.name}}</div>
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div
        class="uk-visible@m tm-grid-expand uk-child-width-1-1 uk-margin-remove-vertical uk-grid uk-grid-stack"
        uk-grid
      >
        <div class="uk-grid-item-match uk-width-1-1@m uk-visible@m uk-first-column" id="page#1-1-0">
          <div class="uk-panel uk-width-1-1">
            <div
              id="page#1-1-0-0"
              class="uk-visible@m uk-position-absolute uk-width-1-1"
              uk-parallax="y: 0,-120;"
              style="left: -3vw; top: -550px;"
            >
              <img
                src="/images/bg-category-left.webp"
                srcset="/images/bg-category-left.webp"
                sizes="(min-width: 360px) 360px"
                data-width="360"
                data-height="778"
                class="el-image"
                alt
                target="!*"
              />
            </div>

            <div
              id="page#1-1-0-1"
              class="uk-visible@m uk-position-absolute uk-width-1-1 uk-text-right"
              uk-parallax="y: 0,-120;"
              style="left: 80px; top: -395px;"
            >
              <img
                src="/images/bg-category-right.webp"
                srcset="/images/bg-category-right.webp"
                sizes="(min-width: 550px) 550px"
                data-width="550"
                data-height="808"
                class="el-image"
                alt
                target="!*"
              />
            </div>
          </div>
        </div>
      </div>

      <div
        class="tm-section-title uk-position-center-left uk-position-medium uk-text-nowrap uk-visible@xl"
      >
        <div class="tm-rotate-180">My Categories</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["items"],
  computed: {
    baseImagePath() {
      return process.env.apiUrl;
    },
  },
};
</script>

<style lang="scss" scoped>
.el-image {
  max-width: 30vw;
}
</style>
