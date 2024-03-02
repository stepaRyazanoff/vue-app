<template>
  <p class="app__item-text">
    Out of the night that covers me,
    <span class="indented-line">Black as the pit from pole to pole,</span><br />
    I thank whatever gods may be
    <span class="indented-line">For my unconquerable soul.</span>
  </p>
</template>

<style scoped>
.app__item-text {
  margin-bottom: 30px;
}

@media (max-width: 800px) {
  .app__item-text {
    margin-bottom: 15px;
  }
}

@media (max-width: 683px) {
  .app__item-text {
    margin-bottom: 10px;
  }
}
</style>

