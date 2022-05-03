<template>
  <div class="home">
    <CustomerText tag="h1">Profile Tag</CustomerText>
  </div>
</template>
<script>
import CustomerText from "@/components/CustomerText.vue";
export default {
  name: "ProfileTag",
  components: {
    CustomerText,
  },
};
</script>
