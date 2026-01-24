import type { svg } from 'property-information';

<template>
  <Head>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Jersey+10&display=swap"
      rel="stylesheet"
    />
  </Head>
  <AppHeader />
  <main>
    <NuxtPage />
  </main>
  <AppFooter></AppFooter>
</template>

<style lang="css">
@import url(~/assets/styles/main.css);
</style>
