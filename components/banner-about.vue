<template>
  <div
    class="uk-section-secondary uk-section"
    uk-scrollspy="target: [uk-scrollspy-class]; cls: uk-animation-slide-top-small; delay: false;"
  >
    <div class="uk-container">
      <div
        class="uk-child-width-1-1 uk-flex uk-flex-center uk-flex-middle"
        uk-grid=""
        uk-height-viewport
      >
        <div class="uk-width-1-1@m">
          <h2
            class="uk-width-2xlarge uk-margin-auto uk-text-center uk-scrollspy-inview"
            uk-scrollspy-class=""
            style=""
          >
            We are Fuse and we create efficient web<br class="uk-visible@s" />
            design and branding.
          </h2>
          <div
            class="uk-margin-medium uk-text-center uk-scrollspy-inview"
            uk-scrollspy-class
            style=""
          >
            <a
              class="el-content uk-button uk-button-text"
              title="Learn more about us"
              href="/themes/wordpress/2016/fuse/index.php?page_id=4"
            >
              Learn more about us
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["items"],
};
</script>
