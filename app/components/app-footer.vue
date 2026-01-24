<script setup>
import { onMounted, onUnmounted, ref } from "vue";
import { useThrottleFn, useWindowSize } from "@vueuse/core";
const { height: windowHeight } = useWindowSize();

watch(windowHeight, () => {
  throttledScrollHandler();
});

const showBackButton = ref(false);
const navigateTop = () => {
  window.scrollTo({
    top: 0,
    left: 0,
    behavior: "smooth",
  });
};
const handleScroll = () => {
  if (window.scrollY > 24) {
    showBackButton.value = true;
  } else {
    showBackButton.value = false;
  }
};
const throttledScrollHandler = useThrottleFn(handleScroll, 100);
onMounted(() => {
  window.addEventListener("scroll", throttledScrollHandler);
});
onUnmounted(() => {
  window.removeEventListener("scroll", throttledScrollHandler);
});
</script>
<template>
  <footer id="contact" class="main-footer">
    <div class="main-footer-section">
      <h2>Contact</h2>
      <a href="mailto:info@survivingpixels.fi">info@survivingpixels.fi</a>
      <br />
      <a href="mailto:surviving.pixels86@gmail.com">
        surviving.pixels86@gmail.com
      </a>
    </div>
    <div class="main-footer-section">
      <h2>Address</h2>
      <p>Tampere, Finland</p>
    </div>
    <button
      v-show="showBackButton"
      class="button-scroll-top"
      @click="navigateTop"
    >
      Back to top
    </button>
  </footer>
</template>

<style scoped>
.main-footer {
  background-color: #210101;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  gap: 1rem;
  padding: 0 2rem 1rem;
  position: relative;
}
.main-footer-section {
  text-align: center;
}
.button-scroll-top {
  position: absolute;
  inset: auto auto 100%;
  background-color: #210101;
}
</style>
