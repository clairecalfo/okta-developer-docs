<template>
  <header class="redesign">
    <a href="https://developer.okta.com/" class="header--logo">
      <img src="/img/icons/okta-developer.svg" />
    </a>
    <input type="text" placeholder="Search Developer" class="temp-search" />
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
  </header>
</template>

<script>
export default {
  components: {
    MenuItems: () => import("../components/MenuItems.vue"),
    MenuItem: () => import("../components/MenuItem.vue")
  }
};
</script>
