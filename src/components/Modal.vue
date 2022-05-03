<template>
  <div class="Modal">
    <div class="row">
      <div class="col-lg-3">
        <router-link to="/profile">
          <Avatar :size="50" />
        </router-link>
      </div>
      <div class="col-lg-4 username">
        <div>
          <router-link to="/profile">
            <CustomText tag="b">{{ username }}</CustomText>
          </router-link>
        </div>
        <div>
          <CustomText>{{ fullName }}</CustomText>
        </div>
      </div>
      <div class="col-lg-5 profil-eye">
        <router-link to="/profile">
          <button type="button">
            <CustomText>Profili Gör</CustomText>
          </button>
        </router-link>
      </div>
    </div>
  </div>
</template>
<script>
import Avatar from "@/components/Avatar.vue";
import CustomText from "@/components/CustomerText.vue";
export default {
  name: "ModalPage",
  components: {
    Avatar,
    CustomText,
  },
  data() {
    return {
      username: "enesaslann0_",
      fullName: "Enes Aslan",
    };
  },
};
</script>
<style lang="postcss" scoped>
.username {
  justify-content: center;
  text-align: center;
  margin-left: -35px;
  margin-top: 5px;
  span {
    color: grey;
  }
  b {
    margin-left: -17px;
  }
}
.profil-eye {
  margin-top: 15px;
  span {
    color: rgb(var(--d69));
    font-size: 14px;
    font-weight: 600;
    justify-content: center;
    align-items: center;
  }
}
</style>
