<template>
  <header class="header">
    <Container class="header-inner">
      <router-link to="/" class="logo">
        <img
          src="https://www.instagram.com/static/images/web/mobile_nav_type_logo-2x.png/1b47f9d0e595.png"
          alt=""
          height="30"
        />
      </router-link>
      <!-- search -->
      <form class="search">
        <input type="text" placeholder="Search" />
      </form>
      <nav class="navigation">
        <router-link to="/">
          <IconHomeActive v-if="$route.name == 'home'" />
          <IconHome v-else />
        </router-link>
        <router-link to="/direct">
          <IconDirectActive v-if="$route.name == 'direct'" />
          <IconDirect v-else />
        </router-link>
        <router-link to="/explore">
          <IconExploreActive v-if="$route.name == 'explore'" />
          <IconExplore v-else />
        </router-link>
        <router-link to="/profile">
          <Avatar :size="30" />
        </router-link>
      </nav>
    </Container>
  </header>
</template>
<script>
import IconHome from "@/components/svg/home";
import IconHomeActive from "@/components/svg/homeActive";

import IconExplore from "@/components/svg/explore";
import IconExploreActive from "@/components/svg/exploreActive";

import IconDirect from "@/components/svg/direct";
import IconDirectActive from "@/components/svg/directActive";

import Container from "@/components/Container";

import Avatar from "@/components/Avatar.vue";
export default {
  name: "HeaderPage",
  components: {
    IconHome,
    IconHomeActive,
    IconExplore,
    IconExploreActive,
    IconDirect,
    IconDirectActive,
    Container,
    Avatar,
  },
};
</script>
<style scoped>
.header {
  z-index: 90;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  background-color: white;
  border-bottom: 1px solid rgb(var(--b6a));
}

.header-inner {
  height: var(--header-height);
  display: flex;
  align-items: center;
  justify-content: center;

  @media (--t) {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    align-items: center;
  }
}

.logo {
  font-size: 1.6rem;
  font-weight: bold;
}

.search {
  display: none;

  @media (--t) {
    display: block;
    text-align: center;

    input {
      width: 215px;
      height: 28px;
      border: 1px solid rgb(var(--b6a));
      background-color: rgb(var(--b3f));
      border-radius: 4px;
      padding-left: 20px;
      padding-right: 20px;
    }
  }
}
.navigation {
  z-index: 90;
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: white;
  border-top: 1px solid rgb(var(--b6a));
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: space-around;

  @media (--t) {
    height: auto;
    border: 0;
    position: static;
    justify-content: flex-end;

    a {
      margin-left: 20px;
    }
  }
}
</style>
