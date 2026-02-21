<script setup>
import Header from './components/Header.vue'
import About from './components/About.vue'
import Article from './components/Article.vue';
import Navigation from './components/Navigation.vue';

</script>

<template>
  <Header />
  <div class="flex-container">
    <Navigation />
    <div class="flex-maincolumn">
      <div class="textBox">
        <About />
        <h1 id="projects">My Projects</h1>
        <Article aId="VrAirships" title="VR Airships"
          text="This is my latest project I am working on. It is a VR Game where you pilot a steampunk airship through various missions. The game is created with Unity and all assets are done by me."
          :imgs="[
            'src/assets/shippair1.JPG',
            'src/assets/shippair3.JPG',
            'src/assets/shippair2.JPG'
          ]" />
        <Article aId="OnionWar" title="OnionWar"
          text="This is a tactical shooter game with roleplay elements. Work in progress but first playable multiplayer version is ready."
          reference="https://github.com/GandrLu/Cooling-Module-Game" :imgs="[
            'src/assets/OnionWarRunning.gif',
            'src/assets/OnionWarShooting.gif',
          ]" :vVids="[
            'https://player.vimeo.com/video/503239354',
            'https://player.vimeo.com/video/503683148'
          ]" />
        <Article aId="Coolingsystem" title="Cooling System Module Game"
          text="This is a mini game that represents the cooling system of a PC. It is part of a bigger system with other computer components as (multiplayer) mini games, but this video shows only the fuctionality of the cooling system isolated, which was my part. The game and all assets are done by me (with 3DS Max and Unity) except:"
          reference="https://github.com/GandrLu/Cooling-Module-Game" :listing="[
            'Player (Model, Anims, Movement)',
            'Music: Benjamin TISSOT bensound.com',
            'SoundFX: soundbible.com'
          ]" :vVids="[
            'https://player.vimeo.com/video/322762717'
          ]" />
        <Article aId="BrickBreaker" title="Brick breaker game - C++ and qt"
          text="This is a simple brick breaker game made with C++ and qt. I kept the art style very simple (all was done by me) as I wanted to focus on learning qt."
          reference="https://github.com/GandrLu/BrickBall" :imgs="[
            'src/assets/BrickBall_Title.png',
            'src/assets/BrickBall_Game1.png'
          ]" />
        <Article aId="Taxiii" title="Taxiii"
          text="A litte android mobile game prototype where you steer a taxi through the traffic. The traffic and obstacles are generated randomly and the taxi drives continuously faster over time. The game is created with unity by using assets from synty studios."
          :vVids="[
            'https://player.vimeo.com/video/409808341'
          ]" />
        <Article aId="bearpong" title="BearPong - MiniGameJam Berlin 11/2019"
          text="We made this little game where you take bears to the moon. Thanks to my teammates for this fun little project. Press the left mousebutton to charge a catapult and release it to shoot. Levels are randomly generated, when too hard, reload the page. Reach the moon!"
          reference="/bearpong/index.html"
          :imgs="[
            'src/assets/bearpong1.JPG',
            'src/assets/bearpong2.JPG'
          ]" />
      </div>
      <div style="height: 60px"></div>
    </div>
    <p class="footer">
      © 2026 Luzius Koelling - GandrLu - All rights reserved.
    </p>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
