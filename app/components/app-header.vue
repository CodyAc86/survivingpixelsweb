<template>
  <header>
    <nav>
      <NuxtLink to="/">
        <img
          src="~/assets/svg/Surviving Pixels Logo.svg"
          class="main-logo"
          alt="Surviving Pixels logo"
        />
      </NuxtLink>
      <div class="main-nav-links">
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="about">About</NuxtLink>
        <NuxtLink to="/portfolio">Portfolio</NuxtLink>
        <NuxtLink to="contact">Contact</NuxtLink>
        <!-- <a href="#contact">Contact</a> -->
      </div>
    </nav>
  </header>
</template>
<style scoped>
.main-logo {
  margin: 0;
  padding: 0;
  max-width: 12.5rem;
  width: 100%;
  height: auto;
}
.main-nav-links {
  display: flex;
  gap: 8rem;
  flex-grow: 1;
  flex-shrink: 1;
  max-width: 25rem;
  gap: 1rem;
  justify-content: space-between;
  padding: 0 1rem;
  a {
    font-size: 1.5rem;
  }
}
</style>
