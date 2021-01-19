<template>
  <header>
    <div class="h">
      <div class="h__logo">nisestagram</div>
      <div class="h__icons">
        <img src="../assets/ico_plus.svg" alt="nice" width="24" height="24" />
        <img src="../assets/ico_nice.svg" alt="nice" width="24" height="24" />
        <img src="../assets/ico_send.svg" alt="nice" width="24" height="24" />
      </div>
    </div>
  </header>
</template>

<style lang="scss">
  header {
    position: sticky;
    top: 0;
    background: #fff;
    z-index: 1;
    height: 48px;
  }
  .h {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 8px;
    height: 100%;

    &__logo {
      font-family: 'Pacifico';
      font-size: 24px;
    }

    &__icons {
      display: flex;

      img {
        margin: 0 8px;
      }
    }
  }
</style>