<template>
  <div class="card">
    <!-- card header -->
    <div class="card__h">
      <div class="card__h__user">
        <img src="../assets/sampleicon.jpg" alt="icon" width="32" height="32" />
        <div>
          {{ username }}
        </div>
      </div>
      <img class="card__h__menu" src="../assets/ico_menu.svg" alt="menu" width="16" height="16" />
    </div>
    <!-- 写真 -->
    <div class="card__img">
      <img :src="img" alt="sampleimage" width="375" height="480" />
    </div>
    <!-- アクション / indicator -->
    <div class="card__action">
      <div class="card__action__iconList">
        <img src="../assets/ico_nice.svg" alt="nice" width="24" height="24" @click="onNiceClick" />
        <img src="../assets/ico_comment.svg" alt="nice" width="24" height="24" v-on:click="onCommentClick" />
        <img src="../assets/ico_send.svg" alt="nice" width="24" height="24" />
      </div>
    </div>
    <!-- テキスト -->
    <div class="card__desc">
      <span class="card__desc__name">{{ username }}</span>
      {{ text }}
    </div>
    <!-- ナイス件数 -->
    <div v-show="niceCount" class="card__nice">
      {{ niceCount }}件のnice!
    </div>
    <!-- コメントリスト -->
    <ul class="card__comments">
      <li v-for="(comment, index) in comments" :key="index">{{ comment }}</li>
      <li v-if='!hasComments'>まだコメントはありません。</li>
    </ul>
    <!-- コメント入力フォーム -->
    <div class="card__form" v-show="showCommentInput">
      <input type="text" v-model="enteringComment" placeholder="ナイスなコメントを入力" />
      <img src="../assets/ico_send.svg" alt="nice" width="20" height="20" @click="onCommentSend" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'card',
  props: ['username', 'img', 'text'],
  data() {
    return {
      showCommentInput: false,
      enteringComment: '',
      comments: [],
      niceCount: 0
    }
  },
  computed: {
    hasComments() {
      return this.comments.length;
    }
  },
  methods: {
    onCommentClick() {
      this.showCommentInput = !this.showCommentInput;
    },
    onCommentSend() {
      this.comments.push(this.enteringComment);
      this.enteringComment = '';
      this.showCommentInput = !this.showCommentInput;
    },
    onNiceClick() {
      this.niceCount++;
    }
  }
}
</script>

<style lang="scss">
.card {
  &__h {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 8px 16px 8px 8px;

    &__user {
      display: flex;
      align-items: center;
      font-weight: 600;
      font-size: 12px;

      img {
        border-radius: 50%;
        position: relative;
        margin-right: 8px;
      }
    }

    &__menu {
      transform: rotate(90deg);
    }
  }

  &__img {
    img {
      object-fit: cover;
    }
  }

  &__action {
    display: flex;
    margin-top: 16px;

    &__iconList {
      display: flex;
      justify-content: space-around;
      width: 112px;
    }
  }

  &__desc {
    font-family: "Hiragino Kaku Gothic Pro";
    font-size: 12px;
    line-height: 1.5;
    margin: 8px;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2;
    overflow: hidden;

    &__name {
      font-weight: 600;
    }
  }

  &__nice {
    font-size: 10px;
    margin: 8px;
    color: #555;
  }

  &__comments {
    font-size: 12px;
    line-height: 1.5;
    margin: 8px;

    li {
      overflow: hidden;
      text-overflow: ellipsis;
      white-space: nowrap;
      padding-right: 8px;
    }
  }

  &__form {
    background: #fff;
    position: fixed;
    bottom: 0;
    z-index: 1;
    width: 100%;
    padding: 8px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 12px;
    font-weight: 600;
    padding-right: 16px;

    input {
      color: #555;
      padding: 8px 12px;
      font-size: 14px;
      font-weight: 300;
      border: 1px solid #eee;
      border-radius: 24px;
      width: 90%;
    }
  }
}
</style>