<template>
  <div class="screenshot-gallery"><slot /></div>
</template>

<style scoped>
.screenshot-gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, 7rem);
  justify-content: center;
  gap: 1.5rem 1rem;
  max-width: 60rem;
  margin: 2rem auto 0;
  @media screen and (max-width: 800px) {
    grid-template-columns: repeat(2, minmax(0, 7rem));
  }
}
.screenshot-gallery :slotted(figure) {
  margin: 0;
  text-align: center;
}
.screenshot-gallery :slotted(figcaption) {
  margin-top: 0.5rem;
  font-size: 0.8rem;
  line-height: 1.1;
}
</style>
