<template>
  <div class="card">
    <!-- card header -->
    <div class="card__h">
      <div class="card__h__user">
        <img src="../assets/sampleicon.jpg" alt="icon" width="32" height="32" />
        <div>
          user_hogehoge
        </div>
      </div>
      <img class="card__h__menu" src="../assets/ico_menu.svg" alt="menu" width="16" height="16" />
    </div>
    <!-- 写真 -->
    <div>
      <img src="//placehold.jp/375x470.png" alt="sampleimage" width="375" height="480" />
    </div>
    <!-- アクション / indicator -->
    <div class="card__action">
      <div class="card__action__iconList">
        <img src="../assets/ico_nice.svg" alt="nice" width="24" height="24" />
        <img src="../assets/ico_comment.svg" alt="nice" width="24" height="24" />
        <img src="../assets/ico_send.svg" alt="nice" width="24" height="24" />
      </div>
    </div>
    <!-- テキスト -->
    <div class="card__desc">
      <span class="card__desc__name">user_hogehoge</span>
      # 思い出は写真のネガみたいなものかもって最近思う。# いつか色褪せてしまうのかな。# 帰り道 # いつもありがとう。
    </div>
  </div>
</template>

<script>
export default {
  name: 'card',
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
}
</style>