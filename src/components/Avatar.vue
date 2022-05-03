<template>
  <figure class="avatar" style="margin: auto">
    <img :src="src" :alt="alt" :height="size" :width="size" />
  </figure>
</template>

<script>
export default {
  name: "AvatarIndex",
  props: {
    src: {
      type: String,
      default:
        "https://media-exp1.licdn.com/dms/image/C4D03AQG0M0GgcLBiqQ/profile-displayphoto-shrink_100_100/0/1630053434526?e=1652918400&v=beta&t=1nzy33Mi3_4pk6LqJXcAcehutH4uAl7thHipTCaGLPM",
    },
    alt: {
      type: String,
    },
    size: {
      type: Number,
    },
  },
};
</script>
<style scoped lang="postcss">
.avatar {
  display: inline-flex;
  padding: 2px;
  border-radius: 999px;
  background: linear-gradient(
    219deg,
    rgba(184, 63, 140, 1) 0%,
    rgba(237, 158, 90, 1) 100%
  );

  img {
    border-radius: inherit;
    border: 2px solid white;
  }
}
</style>
