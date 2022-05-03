<template>
  <div class="offer">
    <div class="row">
      <div class="col-lg-6">
        <CustomText>Senin İçin Öneriler</CustomText>
      </div>
      <div class="col-lg-6">
        <CustomText tag="b"> Tümünü Gör</CustomText>
      </div>
    </div>
    <div class="row offer_user" v-for="(entry, key) in users" :key="key">
      <div class="col-lg-3">
        <router-link to="/profile">
          <Avatar :size="30" :src="entry.src" />
        </router-link>
      </div>
      <div class="col-lg-4 username">
        <div>
          <router-link to="/profile">
            <CustomText tag="b">{{ entry.name }}</CustomText>
          </router-link>
        </div>
      </div>
      <div class="col-lg-5 profil-eye">
        <router-link to="/profile">
          <button type="button">
            <CustomText>Takip Et</CustomText>
          </button>
        </router-link>
      </div>
    </div>
    <div class="row">
      <div class="col-lg-12 footer">
        <custom-text>
          Hakkında - Yardım - Basın - API - Cansın Abi - Gizlilik Koşulları -
          Konumlar - Başlıca Hesaplar - Konu Etiketleri - Dil © 2022 INSTAGRAM
          FROM META
        </custom-text>
      </div>
    </div>
  </div>
</template>
<script>
import Avatar from "@/components/Avatar.vue";
import CustomText from "@/components/CustomerText.vue";
export default {
  name: "OfferPage",
  components: {
    Avatar,
    CustomText,
  },
  data() {
    return {
      username: "enesaslan0_",
      fullName: "M.ENES ASLAN",
      users: [
        {
          name: "mehmet43",
          src: "https://media-exp1.licdn.com/dms/image/C4D03AQEtvntXmFR-_Q/profile-displayphoto-shrink_100_100/0/1638210528165?e=1652918400&v=beta&t=X7gh0wFMs6YYbp42sr3M4xi09HzsAwiwFnr1edWdDgk",
        },
        {
          name: "pixart0_",
          src: "https://media-exp1.licdn.com/dms/image/C560BAQF9dEDhKo6T8Q/company-logo_100_100/0/1611851956435?e=1655337600&v=beta&t=OmNOXBSChyBViTU2tL2MWNzWHGnjjWTqxwmqr627Au4",
        },
        {
          name: "togg34_",
          src: "https://media-exp1.licdn.com/dms/image/C4D0BAQFtHecJt3mObw/company-logo_100_100/0/1639826952495?e=1655337600&v=beta&t=C4Ovdm-wOd1K95JXZ1wBsMnA_Kw59vKcW0edRxjhvJ8",
        },
        {
          name: "ekremimamoglu",
          src: "https://media-exp1.licdn.com/dms/image/C4D03AQG-VMkM-wlknw/profile-displayphoto-shrink_100_100/0/1638342049866?e=1652918400&v=beta&t=0bRLBlpkklIMpGWOCbYnziaWmxhbFLDCnH2eVf4jHS8",
        },
        {
          name: "sabancıHol",
          src: "https://media-exp1.licdn.com/dms/image/C560BAQEgTSrJ9lljjg/company-logo_100_100/0/1543220506671?e=1655337600&v=beta&t=JKFuF_LQpwKZ288nlh9xqjZAaD-3Vq9X2L8XWUJdnp0",
        },
      ],
    };
  },
};
</script>

<style lang="postcss" scoped>
.offer {
  padding: 13px 0 0 0;
}
.footer {
  margin-top: 20px;
  color: rgba(var(--edc, 199, 199, 199), 1);
}
.offer_user {
  padding: 13px 0 0 0;
}
span {
  color: rgba(var(--f52, 142, 142, 142), 1);

  font-weight: 600;
}
.username {
  justify-content: center;
  text-align: center;
  margin-left: -70px;
  margin-top: 5px;
  font-size: 12px;
  span {
    color: grey;
  }
  b {
    margin-left: -17px;
  }
}
.profil-eye {
  margin-top: 5px;
  margin-left: 65px;

  span {
    color: rgb(var(--d69));
    font-size: 14px;
    font-weight: 600;
  }
}
</style>
