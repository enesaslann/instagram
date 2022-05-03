<template>
  <div class="home">
    <nav>
      <router-link to="/profile">Post</router-link> |
      <router-link to="/profile/igtv">IGTV</router-link> |
      <router-link to="/profile/save">Save</router-link> |
      <router-link to="/profile/tag">
        <CustomerText>Tag</CustomerText>
      </router-link>
    </nav>
    <router-view />
  </div>
</template>
<script>
import CustomerText from "@/components/CustomerText.vue";
export default {
  name: "ProfileIndex",
  components: {
    CustomerText,
  },
};
</script>
