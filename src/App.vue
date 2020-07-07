<script>
import Cloud1 from './svgComponents/Cloud1'
import Cloud2 from './svgComponents/Cloud2'
import Cloud3 from './svgComponents/Cloud3'
import Cloud4 from './svgComponents/Cloud4'
import Cloud5 from './svgComponents/Cloud5'
import Mountains from './svgComponents/Mountains'
import Hills from './svgComponents/Hills'
import Trees from './svgComponents/Trees'
import WindTrail from './svgComponents/WindTrail'
import Ground from './svgComponents/Ground'
import Wave1 from './svgComponents/Wave1'
import Wave2 from './svgComponents/Wave2'
import Wave3 from './svgComponents/Wave3'
import SeaFloor1 from './svgComponents/SeaFloor1'
import SeaFloor2 from './svgComponents/SeaFloor2'
import SeaFloor3 from './svgComponents/SeaFloor3'
import SeaFloorFilter from './svgComponents/SeaFloorFilter'
import Sand from './svgComponents/Sand'
import Sword from './svgComponents/Sword'

export default {
  name: 'App',
  components: {
    Cloud1,
    Cloud2,
    Cloud3,
    Cloud4,
    Cloud5,
    Mountains,
    Hills,
    Trees,
    WindTrail,
    Ground,
    Wave1,
    Wave2,
    Wave3,
    SeaFloor1,
    SeaFloor2,
    SeaFloor3,
    SeaFloorFilter,
    Sand,
    Sword,
  },
  data() {
    return {
      scrollY: 0,
      background: {
        red: 0,
        green: 135,
        blue: 213,
      },
    }
  },
  created() {
    window.addEventListener('scroll', this.handleScroll)
  },
  destroyed() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      this.scrollY = window.scrollY
      this.background = {
        red: window.scrollY / 2.75,
        green: 135 - window.scrollY / 17,
        blue: 213 - scrollY / 5.4,
      }
    },
  },
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
</style>

<style scoped>
.parallax-container {
  background-color: #0087d5;
  position: fixed;
  width: 800px;
  height: 800px;
  left: 50%;
  transform: translate(-50%, 0);
}

.foreground {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: flex-end;
  overflow: hidden;
  top: 560px;
  height: 1700px;
  width: 100%;
  background-color: #37559c;
}

@media screen and (min-width: 768px) {
  .parallax-container {
    width: 1200px;
    height: 900px;
  }
  .foreground {
    top: 666px;
  }
}

@media screen and (min-width: 1200px) {
  .parallax-container {
    width: 2560px;
    height: 1000px;
  }

  .foreground {
    top: 965px;
  }
}
</style>

<template>
  <div>
    <div
      class="parallax-container"
      v-bind:style="{ background: `rgb(${background.red}, ${background.green}, ${background.blue})` }"
    >
      <Cloud2 v-bind:style="{ transform: `translateY(${-scrollY * 0.2}px)`}" />
      <Cloud4 v-bind:style="{ transform: `translateY(${-scrollY * 0.3}px)`}" />
      <Cloud5 v-bind:style="{ transform: `translateY(${-scrollY * 0.2}px)`}" />
      <Mountains v-bind:style="{ transform: `translateY(${-scrollY * 0.3}px)`}" />
      <Cloud1 v-bind:style="{ transform: `translateY(${-scrollY * 0.3}px)`}" />
      <Cloud3 v-bind:style="{ transform: `translateY(${-scrollY * 0.3}px)`}" />
      <Hills v-bind:style="{ transform: `translateY(${-scrollY * 0.6}px)`}" />
      <Trees v-bind:style="{ transform: `translateY(${-scrollY * 0.8}px)`}" />
      <WindTrail v-bind:style="{ transform: `translateY(${-scrollY * 0.7}px)`}" />
      <Ground v-bind:style="{ transform: `translateY(${-scrollY * 0.9}px)`}" />
      <Wave3 v-bind:style="{ transform: `translateY(${-scrollY * 0.9}px)`}" />
      <Wave2 v-bind:style="{ transform: `translateY(${-scrollY * 0.92}px)`}" />
      <Wave1 v-bind:style="{ transform: `translateY(${-scrollY * 1}px)`}" />
    </div>
    <div class="foreground">
      <SeaFloor3
        style="filter: url('#seaFloorFilter')"
        v-bind:style="{ transform: `translateY(${scrollY * 0.38}px)`}"
      />
      <SeaFloor2
        style="filter: url('#seaFloorFilter')"
        v-bind:style="{ transform: `translateY(${scrollY * 0.25}px)`}"
      />
      <SeaFloor1
        style="filter: url('#seaFloorFilter')"
        v-bind:style="{ transform: `translateY(${scrollY * 0.13}px)`}"
      />
      <SeaFloorFilter />
      <Sword />
      <Sand />
    </div>
  </div>
</template>
