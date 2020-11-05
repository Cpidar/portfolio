<template>
  <div
    class="uk-section-muted uk-section uk-section-large"
    tm-header-transparent="dark"
    uk-scrollspy="target: [uk-scrollspy-class]; cls: uk-animation-slide-bottom-medium; delay: false; hidden: true"
  >
    <div class="uk-container uk-container-xlarge">
      <div class="tm-header-placeholder uk-margin-remove-adjacent"></div>
      <div class="tm-grid-expand uk-margin uk-grid uk-grid-stack" uk-grid>
        <div class="uk-width-1-1@m uk-first-column">
          <h2 class="uk-h3 uk-heading-bullet uk-margin" uk-scrollspy-class>{{title}}</h2>
          <div class="uk-margin-medium">
            <div
              class="uk-child-width-1-1 uk-child-width-1-3@s uk-child-width-1-4@m uk-grid-match uk-grid"
              uk-grid
            >
              <div
                v-for="(item, index) of items"
                :key="index"
              >
                <a
                  class="uk-card uk-card-default uk-link-toggle uk-display-block uk-border-rounded uk-transition-toggle"
                  :href="item.url"
                  uk-scrollspy-class
                >
                  <div class="uk-card-media-top uk-inline-clip uk-border-rounded">
                    <!-- <div class="uk-card-badge uk-label uk-label-warning" v-if="item.focused">{{item.flag}}</div> -->
                    <img
                      class="uk-transition-scale-up uk-transition-opaque"
                      alt
                      :data-src="item.image"
                      :data-srcset="item.image"
                      data-sizes="(min-width: 610px) 610px"
                      data-width="610"
                      data-height="407"
                      uk-img
                      sizes="(min-width: 610px) 610px"
                      :srcset="item.image"
                      :src="item.image"
                    />
                  </div>
                  <div class="uk-card-body uk-margin-remove-first-child">
                    <!-- <p class="uk-text-meta uk-margin-remove-bottom">{{item.category.name}}</p> -->
                    <h3 class="el-title uk-h5 uk-margin-small">{{item.title}}</h3>
                    <!-- <p class="uk-text-meta uk-margin-remove-top"><span class="uk-margin-small-left" uk-icon="location"></span>{{item.neighborhood.name}}</p> -->
                    <!-- <div
                    v-if="item.price"
                      class="el-meta uk-text-meta uk-margin-small-top"
                    >{{"قیمت: " + new Intl.NumberFormat('fa-IR', { maximumSignificantDigits: 3 }).format(item.price) + " تومان"}}</div> -->
                  </div>
                </a>
              </div>
            </div>
          </div>

          <div class="uk-margin-xlarge uk-text-center" uk-scrollspy-class>
            <!-- <ul class="uk-pagination uk-margin-remove-bottom uk-flex-center">
              <li class="uk-active">
                <span>1</span>
              </li>
              <li>
                <a
                  href="https://demo.yootheme.com/themes/wordpress/2020/design-bites/?resource_cat=ui-kits&amp;paged=2"
                >2</a>
              </li>
              <li>
                <a
                  href="https://demo.yootheme.com/themes/wordpress/2020/design-bites/?resource_cat=ui-kits&amp;paged=2"
                  title="Next"
                >
                  <span uk-pagination-next class="uk-icon uk-pagination-next">
                    <svg
                      width="7"
                      height="12"
                      viewBox="0 0 7 12"
                      xmlns="http://www.w3.org/2000/svg"
                      data-svg="pagination-next"
                    >
                      <polyline fill="none" stroke="#000" stroke-width="1.2" points="1 1 6 6 1 11" />
                    </svg>
                  </span>
                </a>
              </li>
            </ul>-->
            <button
              class="uk-button uk-button-danger"
              v-if="HasMore"
              @click="showMore"
            >نمایش موارد بیشتر</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["title", "items", "PageSize", "HasMore"],
  data() {
    return {
      server: process.env.apiUrl,
      page: 0
    };
  },
  computed: {
    baseImagePath() {
      return process.env.apiUrl;
    },
  },
  methods: {
    formatPrice(price) {
      return new Intl.NumberFormat("fa-IR", {
        maximumSignificantDigits: 3
      }).format(price);
    },
    showMore() {
      this.page++;
      this.$emit("fetch", this.page);
    }
  }
};
</script>
