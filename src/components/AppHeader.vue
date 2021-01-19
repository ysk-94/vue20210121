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

<script>
export default {
  name: 'Header',
  data() {

  }
}
</script>

<style lang="scss">
  .h {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 8px;

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