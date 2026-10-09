<template>
  <div>
    <h1>Portfolio</h1>
    <NarrowPage>
      <div class="portfolio-intro">
        <img
          src="~/assets/images/portfolio/aurel-codarcea.webp"
          class="portfolio-intro-photo"
          alt="Aurel Codarcea wearing a gaming headset"
        />
        <div>
          <h2>Aurel Codarcea</h2>
          <p>
            Game and software developer with a Bachelor's degree in Computer
            Applications from HAMK University of Applied Sciences in Finland.
          </p>
        </div>
      </div>
      <p>
        I grew up with MS-DOS and an IBM "286", and have loved PC games ever
        since. After 15 years working as a chef, i decided to turn my passion
        into a profession and started studying game development, first with
        courses from Udemy and GameDev.tv, then at HAMK. Along the way i realised
        that i just love to code, no matter if it's a game or a piece of
        software. I love creating something, making it work the way i want it to,
        finding the problems and solving them. I'm stubborn, and don't give up
        when it gets hard!
      </p>
      <p>
        During my studies and in my free time, i have been working on projects
        both for school and for personal learning. These include programming and
        design of software, games and other fun stuff. Check out some of my work
        so far!
      </p>
    </NarrowPage>

    <div class="portfolio-projects">
      <GameSection>
        <template #splash-image>
          <img
            src="~/assets/images/sparks.webp"
            alt="Splash image for Sparks, the mobile game"
          />
        </template>
        <template #title>Sparks</template>
        <template #description>
          <p>
            A 3D side-scroll platformer made in Unreal Engine 5 for mobile
            devices, and the first game of my company Surviving Pixels. Jump,
            zap and interact with devices to collect sparks, avoid enemy sparks
            and energy-draining obstacles, and beat each level against the
            clock. A leveling system lets players upgrade their spark's energy,
            zap and agility, and progress and highscores are saved.
          </p>
          <p>
            <NuxtLink to="/">Read more and watch the video on the home page</NuxtLink>
          </p>
        </template>
      </GameSection>

      <GameSection>
        <template #splash-image>
          <img
            src="~/assets/images/portfolio/mars-unknown-thumb.webp"
            alt="Mars Unknown logo painted over the planet Mars"
          />
        </template>
        <template #title>Mars Unknown</template>
        <template #description>
          <p>
            Unreal Engine 5 top-down wave-based shooter. I developed it for the
            Game Project course at LUT University of Applied Sciences and have
            kept updating it since i finished my studies. It was made in Unreal
            Engine 5.4 and recently upgraded to 5.6. The player is a marine lost
            on Mars who has to survive as many waves of aliens as possible by
            shooting, running, and picking up ammo and health when available.
          </p>
          <p>
            Since then i have added a leveling system with player stats, the
            option to continue from the reached level or start a new game and
            reset all progress, new visual effects and new UIs to improve the
            player experience.
          </p>
          <p>
            <a href="https://codyac86.itch.io/mars-unknown" target="_blank" rel="noopener noreferrer">
              Download Mars Unknown on itch.io
            </a>
          </p>
          <iframe
            style="width: 100%; height: auto; aspect-ratio: 16 / 9"
            src="https://www.youtube.com/embed/TAmGTFE34Gw"
            title="Mars Unknown game trailer"
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

      <GameSection>
        <template #splash-image>
          <img
            src="~/assets/images/portfolio/vr-exhibition-hamk.webp"
            alt="Digital fashion figure from the HAMK digital fashion project"
          />
        </template>
        <template #title>VR Exhibition</template>
        <template #description>
          <p>
            An Unreal Engine 5 VR project that we developed in a team of two
            during my 6-month internship at HAMK SMART Research Unit in 2024
            (today known as HAMK Tech). It was part of a larger
            <a
              href="https://www.hamk.fi/projektit/alykkyydesta-uutta-vastuullista-muotoilua-muotia-osaamista-ja-liiketoimintaa/"
              target="_blank"
              rel="noopener noreferrer"
            >
              digital fashion project
            </a>. In the VR Exhibition, players navigate using VR gear (headset
            and controllers) and interact with objects and art: picking things
            up, drawing and using UI widgets.
          </p>
          <p>
            My role was to create all the functions and components for the
            interactions between the player and the environment, including
            grabbing and equipping objects, widget interactions, UI/UX, sound
            effects and some visual effects, as well as 3D modelling and
            animation in Blender. I wrote my thesis about the development of this
            project.
          </p>
          <p>
            <a href="https://urn.fi/URN:NBN:fi:amk-202503254932" target="_blank" rel="noopener noreferrer">Read the thesis</a>
          </p>
        </template>
      </GameSection>

      <GameSection>
        <template #splash-image>
          <img
            src="~/assets/images/portfolio/go-to-hell-thumb.webp"
            alt="Go To Hell main menu with a winged cube character wearing a halo"
          />
        </template>
        <template #title>Go To Hell</template>
        <template #description>
          <p>
            An infinite faller game made in Unity 3D during the Introduction to
            Game Development course at HAMK University of Applied Sciences.
          </p>
          <p>
            <a href="https://codyac86.itch.io/go-to-hell" target="_blank" rel="noopener noreferrer">
              Play it in your browser on itch.io
            </a>
          </p>
        </template>
      </GameSection>

      <section>
        <GameSection>
          <template #splash-image>
            <img
              src="~/assets/images/portfolio/baby-feeder-index.webp"
              alt="Baby Feeder app home screen with a cartoon baby holding a bottle"
            />
          </template>
          <template #title>Baby Feeder App</template>
          <template #description>
            <p>
              A mobile app made with React Native and Expo for keeping track of
              a baby's feedings. It uses datetimepicker for selecting the
              feeding times, SQLite for the database and stack navigation
              between screens.
            </p>
            <p>
              <a href="https://github.com/CodyAc86/BabyFeederStacked" target="_blank" rel="noopener noreferrer">
                See the source code on GitHub
              </a>
            </p>
          </template>
        </GameSection>
        <ScreenshotGallery>
          <figure>
            <img
              src="~/assets/images/portfolio/baby-feeder-add-feeding.webp"
              alt="Form for adding a new feeding"
            />
            <figcaption>Adding feeding times</figcaption>
          </figure>
          <figure>
            <img
              src="~/assets/images/portfolio/baby-feeder-select-time.webp"
              alt="Clock picker for choosing the feeding time"
            />
            <figcaption>Selecting the time of the feeding</figcaption>
          </figure>
          <figure>
            <img
              src="~/assets/images/portfolio/baby-feeder-list.webp"
              alt="List of saved feedings"
            />
            <figcaption>Feeding times from the database</figcaption>
          </figure>
          <figure>
            <img
              src="~/assets/images/portfolio/baby-feeder-alert.webp"
              alt="Dialog asking whether to delete or archive a feeding"
            />
            <figcaption>Delete or archive prompt</figcaption>
          </figure>
          <figure>
            <img
              src="~/assets/images/portfolio/baby-feeder-swipe-archive.webp"
              alt="Feeding swiped right, highlighted in yellow"
            />
            <figcaption>Swipe right to archive</figcaption>
          </figure>
          <figure>
            <img
              src="~/assets/images/portfolio/baby-feeder-swipe-delete.webp"
              alt="Feeding swiped left, highlighted in red"
            />
            <figcaption>Swipe left to delete</figcaption>
          </figure>
          <figure>
            <img
              src="~/assets/images/portfolio/baby-feeder-archive.webp"
              alt="List of archived feedings"
            />
            <figcaption>Archive page</figcaption>
          </figure>
        </ScreenshotGallery>
      </section>
    </div>

    <NarrowPage>
      <p class="portfolio-more">
        More projects will be added in the near future as i publish them.
      </p>
      <h2>Get in touch</h2>
      <p>
        Email:
        <a href="mailto:aurel.codarcea86@gmail.com">aurel.codarcea86@gmail.com</a>
        <br />
        LinkedIn:
        <a href="https://www.linkedin.com/in/aurel-codarcea-8b3a77b7/" target="_blank" rel="noopener noreferrer">
          Aurel Codarcea
        </a>
      </p>
    </NarrowPage>
  </div>
</template>

<style scoped>
.portfolio-intro {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  @media screen and (max-width: 800px) {
    flex-direction: column;
    text-align: center;
  }
}
.portfolio-intro-photo {
  width: 8rem;
  flex-shrink: 0;
  border: 0.15rem solid #dbfb27;
}
.portfolio-projects {
  display: grid;
  row-gap: 5rem;
  margin: 4rem 0;
}
.portfolio-more {
  text-align: center;
}
</style>
