<template>
  <h1>Surviving pixels</h1>
  <GameSection>
    <template #splash-image>
      <img
        src="~/assets/images/sparks.webp"
        alt="Splash image for Sparks, the mobile game"
      />
    </template>
    <template #title>Sparks - a mobile game</template>
    <template #description>
      <p>
        Sparks is a mobile 3D side-scroller singleplayer game where you play as an electric
        spark that jumps and zaps. There is a leveling system where you can
        upgrade your spark to be faster and more powerful. You need to jump,
        collect sparks, interact with objects and devices, run away or fight
        enemies to increase your score and complete the level in as little time
        as possible. The demo version of this game contains 5 levels to play and
        will be published to Epic Games store soon. The full-version of the game
        is still being developed and as a part-time indie developer i cannot
        estimate the complete game release date just yet.
      </p>
      <iframe
        style="width: 100%; height: auto; aspect-ratio: 16 / 9"
        src="https://www.youtube.com/embed/0DsThSEotpo?si=jPLAFP3LndWemxU-"
        title="YouTube video player"
        frameborder="0"
        allow="
          accelerometer;
          autoplay;
          clipboard-write;
          encrypted-media;
          gyroscope;
          picture-in-picture;
          web-share;
        "
        referrerpolicy="strict-origin-when-cross-origin"
        allowfullscreen
      ></iframe>
    </template>
  </GameSection>
  <section class="game-section"></section>
</template>
