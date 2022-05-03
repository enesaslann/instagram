<template>
  <div class="home">
    <div class="timeline">
      <div class="slider">
        <Slider />
      </div>
      <div class="post" v-for="(value, key) in posts" :key="key">
        <Post
          :img="value.src"
          :post="value.post"
          :username="value.username"
          :location="value.location"
          :message="value.message"
        />
      </div>
    </div>

    <div class="sidebar">
      <Modal />
      <Offer />
    </div>
  </div>
</template>
<script>
import Slider from "@/components/Slider.vue";
import Post from "@/components/Post.vue";
import Modal from "@/components/Modal.vue";
import Offer from "@/components/Offer.vue";
export default {
  name: "HomeIndex",
  components: {
    Slider,
    Post,
    Modal,
    Offer,
  },
  data() {
    return {
      post: 10,
      posts: [
        {
          src: "https://yt3.ggpht.com/ytc/AKedOLSBbdMgyxWru4DSTQYJSvdNvVe31sVWNJIPN0xl3A=s176-c-k-c0x00ffffff-no-rj-mo",
          post: "https://menesaslan.net/a.jpeg",
          username: "roportajadam ",
          location: null,
          message: "- Beni pahalı bir mekana götür + olur hayatım",
        },
        {
          src: "https://media-exp1.licdn.com/dms/image/C4D03AQG0M0GgcLBiqQ/profile-displayphoto-shrink_100_100/0/1630053434526?e=1652918400&v=beta&t=1nzy33Mi3_4pk6LqJXcAcehutH4uAl7thHipTCaGLPM",
          post: "https://media-exp1.licdn.com/dms/image/C4D22AQEaFUjkEFYEfg/feedshare-shrink_800/0/1645989630418?e=1649894400&v=beta&t=VmY8daRPf_B4s8KBGda9sEdpUq8iCkcwGS-fQsYUBiw",
          username: "enesaslan0_",
          location: null,
          message:
            "ThinkPad X Serisi ile etkin performans ve üstün mobiliteyi keşfedin",
        },
        {
          src: "https://media-exp1.licdn.com/dms/image/C4D0EAQEn1WCg4sRrSw/rightRail-logo-shrink_200_200/0/1646920998275?e=1647270000&v=beta&t=beRTsAXTFv7_uSwo7-JMX4oZf1s1hEKcTjmWi8E6edc",
          post: "https://media-exp1.licdn.com/dms/image/C4E22AQEWfzcxfP19dA/feedshare-shrink_800/0/1647087666125?e=1649894400&v=beta&t=-HgszKEsHrtz2wWfAjU1qSkAXdE3uIyYu1FkGE0nmhI",
          username: "enesaslan0_",
          location: null,
          message: "- Beni pahalı bir mekana götür + olur hayatım",
        },
      ],
    };
  },
};
</script>
<style lang="postcss">
.post {
  margin-bottom: 20px;
}
.home {
  max-width: 605px;
  margin-left: auto;
  margin-right: auto;

  @media (--t) {
    max-width: none;
    display: grid;
    grid-template-columns: 1fr 295px;
    grid-gap: 30px;
  }
}
.sidebar {
  display: none;
  @media (--t) {
    width: 400px;
    position: fixed;
    margin-left: 625px;
    display: block;
  }
}
</style>
