<template>
  <header class="redesign">
    <a href="https://developer.okta.com/" class="header--logo">
      <img src="/img/icons/okta-developer.svg" />
    </a>
    <div :class="{ 'input--slideout': true, opened: searchOpened }">
      <div class="input--wrapper">
        <img class="input--icon" src="/img/icons/search.svg" />
        <input
          class="input--field"
          type="text"
          placeholder="Search Developer"
        />
      </div>
    </div>
    <div class="header--links">
      <MenuItems
        :items="$themeConfig.redesign.primary_left_nav"
        :itemCss="'link link--small link--semi-bold'"
        :subItemCss="'link link--small link--semi-bold link--black'"
      />
      <MenuItems
        :items="$themeConfig.redesign.primary_right_nav"
        :itemCss="'link link--small link--semi-bold'"
        :subItemCss="'link link--small link--semi-bold link--black'"
      />
    </div>
    <a class="sign-up--button" href="/signup/">Sign Up</a>
    <div class="mobile--toggles">
      <div class="mobile--toggle" @click="searchOpened = !searchOpened">
        <img src="/img/icons/icon--search-white.svg" />
      </div>
      <div class="mobile--toggle" @click="menuOpened = !menuOpened">
        <img src="/img/icons/icon--menu.svg" />
      </div>
    </div>
  </header>
</template>

<script>
export default {
  components: {
    MenuItems: () => import("../components/MenuItems.vue"),
    MenuItem: () => import("../components/MenuItem.vue")
  },
  data() {
    return {
      searchOpened: false,
      menuOpened: false
    };
  },
  mounted() {
    window.addEventListener("resize", this.handleResize);
  },
  methods: {
    toggleSearch: function() {
      this.searchOpened = !this.searchOpened;
      this.menuOpened = false;
    },
    toggleMenu: function() {
      this.menuOpened = !this.menuOpened;
      this.searchOpened = false;
    },
    handleResize: function() {
      if (window.innerWidth >= 768) {
        this.searchOpened = false;
        this.menuOpened = false;
      }
    }
  }
};
</script>
