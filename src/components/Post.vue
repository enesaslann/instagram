<template>
  <div class="row">
    <div class="col-lg-12">
      <div class="post">
        <!-- header -->
        <header class="header section">
          <div class="header-author">
            <router-link to="/profile"
              ><Avatar :size="40" :src="img"
            /></router-link>
            <div class="header-author-info">
              <div>
                <router-link to="/profile">
                  <CustomText tag="b">{{ username }}</CustomText>
                </router-link>
              </div>
              <div v-show="location !== null">
                <CustomText size="xsmall">{{ location }}</CustomText>
              </div>
            </div>
          </div>
          <div class="header-more">
            <button type="button">
              <IconMore />
            </button>
          </div>
        </header>

        <!-- media -->
        <div class="post-media">
          <img :src="post" alt="" />
        </div>

        <!-- actions -->
        <div class="action-buttons section">
          <button type="button">
            <IconLike
              @click="
                fav = 1;
                like_number++;
              "
              v-if="fav == 0"
            />
            <IconLikeActive
              @click="
                fav = 0;
                like_number--;
              "
              v-else
            />
          </button>
          <button type="button">
            <IconComment />
          </button>
          <button type="button">
            <IconDirect />
          </button>
          <button class="action-save" type="button">
            <IconSave @click="save = 1" v-if="save == 0" />
            <IconSaveActive @click="save = 0" v-else />
          </button>
        </div>

        <!-- view count -->

        <div class="view-count section">
          <custom-text tag="b">{{ like_number }} beğenme</custom-text>
        </div>

        <!-- user message -->

        <div class="user-message section">
          <router-link to="/profile">
            <custom-text tag="b">{{ username }} </custom-text>
          </router-link>
          <custom-text>{{ message }}</custom-text>
        </div>

        <!-- comment list -->

        <div class="comment-list section">
          <custom-text tag="span">
            {{ commentTotal }} yorumun tümünü gör
          </custom-text>
        </div>

        <!-- datetime -->

        <div class="time section">
          <custom-text tag="span"> {{ time }} dakika önce </custom-text>
        </div>

        <!-- comment form -->

        <div class="comment-form section">
          <div class="row">
            <div class="col-lg-1">
              <IconEmoji />
            </div>
            <div class="col-lg-9">
              <input
                type="text"
                placeholder="Yorum ekle..."
                class="form-control"
              />
            </div>
            <div class="col-lg-2">
              <button type="button">
                <custom-text tag="span"> Paylaş</custom-text>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Avatar from "@/components/Avatar";
import CustomText from "@/components/CustomerText";
import IconMore from "@/components/svg/more";
import IconLike from "@/components/svg/like";
import IconLikeActive from "@/components/svg/likeActive";
import IconComment from "@/components/svg/comment";
import IconDirect from "@/components/svg/direct";
import IconSave from "@/components/svg/save";
import IconSaveActive from "@/components/svg/saveActive";
import IconEmoji from "@/components/svg/emoji";
export default {
  name: "PostPage",
  components: {
    IconLike,
    IconLikeActive,
    IconComment,
    IconDirect,
    IconSave,
    IconSaveActive,
    IconMore,
    CustomText,
    Avatar,
    IconEmoji,
  },
  props: {
    img: {
      type: String,
      default:
        "https://media-exp1.licdn.com/dms/image/C4D03AQG0M0GgcLBiqQ/profile-displayphoto-shrink_100_100/0/1630053434526?e=1652918400&v=beta&t=1nzy33Mi3_4pk6LqJXcAcehutH4uAl7thHipTCaGLPM",
    },
    post: {
      type: String,
    },
    username: {
      type: String,
    },
    location: {
      type: String,
    },
    message: {
      type: String,
    },
  },
  data() {
    return {
      save: "0",
      fav: "0",
      like_number: 462.122,
      commentTotal: 2.2021,
      time: 20,
    };
  },
};
</script>

<style scoped lang="postcss">
.post {
  border-radius: 3px;
  border: 1px solid rgb(var(--b6a));
  background-color: white;
}

.section {
  padding-left: 16px;
  padding-right: 16px;
}

.header {
  height: 60px;
  display: flex;
  align-items: center;

  &-author {
    display: flex;
    align-items: center;

    &-info {
      margin-left: 8px;
    }
  }

  &-more {
    margin-left: auto;
  }
}

.action-buttons {
  height: 45px;
  display: flex;
  align-items: center;

  button {
    margin-right: 16px;
  }

  .action-save {
    margin-left: auto;
    margin-right: 0;
  }
}
.user-message {
  padding: 10px 16px 10px 16px;
}
.comment-list {
  padding: 0px 16px 10px 16px;
  span {
    color: grey;
  }
}
.time {
  padding: 0px 16px 10px 16px;
  span {
    color: grey;
    font-size: 10px;
  }
}

.comment-form {
  padding: 6px 16px 6px 16px;
  border-top: 1px solid rgb(var(--ce3));
  input {
    border: 0;
  }
  input:active {
    border: 0;
  }
  span {
    color: rgb(var(--d69));
    font-size: 14px;
    font-weight: 600;
    justify-content: center;
    align-items: center;
  }
}
</style>
