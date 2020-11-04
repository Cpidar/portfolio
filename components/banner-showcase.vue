<template>
  <div
    class="uk-section-secondary"
    tm-header-transparent="light"
    uk-scrollspy="target: [uk-scrollspy-class]; cls: uk-animation-fade; delay: false;"
  >
    <div
      data-src="/images/home-bg.webp"
      data-sizes="(max-aspect-ratio: 2560/1440) 178vh"
      uk-img=""
      class="uk-background-norepeat uk-background-cover uk-background-center-center uk-section uk-section-xlarge uk-flex"
      uk-height-viewport="offset-top: true;"
      style="
        min-height: calc(100vh - 100px);
        background-image: url('/images/home-bg.webp');
      "
    >
      <div class="uk-position-relative uk-width-1-1 uk-flex uk-flex-middle">
        <div class="uk-width-1-1">
          <div class="uk-container">
            <div
              class="tm-grid-expand uk-grid-margin uk-grid uk-grid-stack"
              uk-grid=""
            >
              <div class="uk-width-1-2@m"></div>

              <div class="uk-width-1-2@m">
                <h1
                  class="uk-heading-medium uk-width-xlarge uk-scrollspy-inview"
                  uk-scrollspy-class
                  style=""
                >
                  Mostafa Moazeni<br />
                  is a Designer<br class="uk-visible@s" />
                  &amp; Developer in Dehaghan
                </h1>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SearchBox from "~/components/search-box.vue";

export default {
  components: {
    SearchBox,
  },
  props: ["showcase", "items"],
  data() {
    return {
      server: process.env.apiUrl,
    };
  },
};
</script>

<style scoped>
</style>
