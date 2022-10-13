<template>
  <div class="v-card v-sheet theme--light">
  <div class="v-card__title">Minha Lista</div>
  <div class="v-card__text my-list">
    <ul>
      <li>Text</li>
      <li>Text</li>
      <li>Text</li>
      <li>Text</li>
    </ul>
  </div>
</div>
</template>

<script>
export default {
    name: 'myList',
}
</script>

<style scoped>
.my-list {
    height: calc(100vh - 200px);
    overflow-y: auto !important;
}

</style>