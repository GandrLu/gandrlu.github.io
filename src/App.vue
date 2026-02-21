<script setup>
import Header from './components/Header.vue'
import About from './components/About.vue'
import Article from './components/Article.vue';
import Navigation from './components/Navigation.vue';

// Import images dynamically
import lyriquiz1 from './assets/lyriquiz1_portrait.JPG'
import shippair1 from './assets/shippair1.JPG'
import shippair2 from './assets/shippair2.JPG'
import shippair3 from './assets/shippair3.JPG'
import onionwarRunning from './assets/OnionWarRunning.gif'
import onionwarShooting from './assets/OnionWarShooting.gif'
import brickballTitle from './assets/BrickBall_Title.png'
import brickballGame from './assets/BrickBall_Game1.png'
import bearpong1 from './assets/bearpong1.JPG'
import bearpong2 from './assets/bearpong2.JPG'

</script>

<template>
  <Header />
  <div class="flex-container">
    <Navigation />
    <div class="flex-maincolumn">
      <div class="textBox">
        <About />
        <h1 id="projects">My Projects</h1>
        <Article aId="lyriquiz" title="Lyriquiz - A Lyric based Song Quiz"
          text="A vue.js web app that offers a lyric based song quiz. It uses the spotify and the lrclib.net api to generate personalised questions."
          :imgs="[
            lyriquiz1
          ]"
          :reference="{text: 'Try it here', link: 'https://lyriquiz-2aea0.web.app'}" />
        <Article aId="VrAirships" title="VR Airships"
          text="This is my latest VR project I am working on. It is a VR Game where you pilot a steampunk airship through various missions. The game is created with Unity and all assets are done by me."
          :imgs="[
            shippair1,
            shippair3,
            shippair2
          ]" />
        <Article aId="OnionWar" title="OnionWar"
          text="This is a tactical shooter game with roleplay elements. Work in progress but first playable multiplayer version is ready."
          :reference="{text: 'See the GitHub Project', link: 'https://github.com/GandrLu/Cooling-Module-Game'}"
          :imgs="[
            onionwarRunning,
            onionwarShooting,
          ]" :vVids="[
            'https://player.vimeo.com/video/503239354',
            'https://player.vimeo.com/video/503683148'
          ]" />
        <Article aId="Coolingsystem" title="Cooling System Module Game"
          text="This is a mini game that represents the cooling system of a PC. It is part of a bigger system with other computer components as (multiplayer) mini games, but this video shows only the fuctionality of the cooling system isolated, which was my part. The game and all assets are done by me (with 3DS Max and Unity) except:"
          :reference="{text: 'See the GitHub Project', link: 'https://github.com/GandrLu/Cooling-Module-Game'}"
          :listing="[
            'Player (Model, Anims, Movement)',
            'Music: Benjamin TISSOT bensound.com',
            'SoundFX: soundbible.com'
          ]" :vVids="[
            'https://player.vimeo.com/video/322762717'
          ]" />
        <Article aId="BrickBreaker" title="Brick breaker game - C++ and qt"
          text="This is a simple brick breaker game made with C++ and qt. I kept the art style very simple (all was done by me) as I wanted to focus on learning qt."
          :reference="{text: 'See the GitHub Project', link: 'https://github.com/GandrLu/BrickBall'}"
          :imgs="[
            brickballTitle,
            brickballGame
          ]" />
        <Article aId="Taxiii" title="Taxiii"
          text="A litte android mobile game prototype where you steer a taxi through the traffic. The traffic and obstacles are generated randomly and the taxi drives continuously faster over time. The game is created with unity by using assets from synty studios."
          :vVids="[
            'https://player.vimeo.com/video/409808341'
          ]" />
        <Article aId="bearpong" title="BearPong - MiniGameJam Berlin 11/2019"
          text="We made this little game where you take bears to the moon. Thanks to my teammates for this fun little project. Press the left mousebutton to charge a catapult and release it to shoot. Levels are randomly generated, when too hard, reload the page. Reach the moon!"
          :reference="{text: 'Play it here!', link: '/bearpong/index.html'}"
          :imgs="[
            bearpong1,
            bearpong2
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
