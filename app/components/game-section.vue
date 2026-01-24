<template>
  <section class="game-section">
    <picture class="game-section-splash-image">
      <slot name="splash-image"></slot>
    </picture>
    <h2 class="game-section-title"><slot name="title"></slot></h2>
    <div class="game-section-description">
      <slot name="description"></slot>
    </div>
  </section>
</template>

<style scoped>
.game-section {
  display: grid;
  column-gap: 2rem;
  max-width: 60rem;
  margin: 0 auto;
  grid-template:
    "splash title" 4rem
    "splash description" auto
    / 1fr 1fr;
  @media screen and (max-width: 800px) {
    grid-template:
      "title" auto
      "splash" auto
      "description" auto;
  }
}
.game-section-splash-image {
  grid-area: splash;
}
.game-section-title {
  grid-area: title;
}
.game-section-description {
  grid-area: description;
}
</style>
