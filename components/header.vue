<template>
  <div>
    <!-- NAV -->
    <div class="nav" data-uk-sticky="cls-active: uk-background-secondary uk-box-shadow-medium; top: 100vh; animation: uk-animation-slide-top">
      <div class="uk-container uk-position-top" style="z-index: 1000">
        <nav class="uk-navbar uk-navbar-container uk-navbar-transparent" data-uk-navbar>
          <div class="uk-navbar-left">
            <div class="uk-navbar-item uk-padding-remove-horizontal">
              <a class="uk-logo" title="bertoseeds" href=""><img width="50px" src="/images/logo.svg" alt="Logo"></a>
            </div>
          </div>
          <div class="uk-navbar-right">
            <ul class="uk-navbar-nav uk-visible@s">
              <li class="uk-active uk-visible@m"><a href="" data-uk-icon="home"></a></li>
              <li v-for="item in items" :key="item.id">
                <a :href="item.url" :data-uk-icon="item.submenu.length > 0 ? 'chevron-down' : ''">{{item.name}}</a>
                <div v-if="item.submenu.length > 0" class="uk-navbar-dropdown">
                  <ul class="uk-nav uk-navbar-dropdown-nav">
                    <li v-for="m in item.submenu" :key="m.id"><a :href="m.url">{{m.name}}</a></li>
                  </ul>
                </div>
              </li>
            </ul>
            <a class="uk-navbar-toggle uk-navbar-item uk-hidden@s" data-uk-toggle data-uk-navbar-toggle-icon href="#offcanvas-nav"></a>
          </div>
        </nav>
      </div>
    </div>
    <!-- NAV -->

    <!-- OFFCANVAS -->
		<div id="offcanvas-nav" data-uk-offcanvas="flip: true; overlay: false">
			<div class="uk-offcanvas-bar uk-offcanvas-bar-animation uk-offcanvas-slide">
				<button class="uk-offcanvas-close uk-close uk-icon" type="button" data-uk-close></button>
				<ul class="uk-nav uk-nav-default">
					<li class="uk-active"><a href="#">Active</a></li>
					<li class="uk-parent">
						<a href="#">Parent</a>
						<ul class="uk-nav-sub">
							<li><a href="#">Sub item</a></li>
							<li><a href="#">Sub item</a></li>
						</ul>
					</li>
					<li class="uk-nav-header">Header</li>
					<li><a href="#js-options"><span class="uk-margin-small-right uk-icon" data-uk-icon="icon: table"></span> Item</a></li>
					<li><a href="#"><span class="uk-margin-small-right uk-icon" data-uk-icon="icon: thumbnails"></span> Item</a></li>
					<li class="uk-nav-divider"></li>
					<li><a href="#"><span class="uk-margin-small-right uk-icon" data-uk-icon="icon: trash"></span> Item</a></li>
				</ul>
				<h3>Title</h3>
				<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
			</div>
		</div>
		<!-- /OFFCANVAS -->
  </div>
</template>

<script>
export default {
  props: ["items"],
  data() {
    return {
      categories: [],
      menu: [
        { label: "خانه", href: "/" },
        { label: "مجله سقف و سرا", href: "/blog" },
      ],
    };
  },
};
</script>

<style scoped>
.tm-header-overlay {
  position: absolute;
  left: 0;
  right: 0;
  z-index: 980;
}

.uk-navbar-sticky {
  background-color: white !important;
}
</style>
