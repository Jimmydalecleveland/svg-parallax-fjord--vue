<script>
import Cloud1 from './svgComponents/Cloud1'
import Cloud2 from './svgComponents/Cloud2'
import Cloud3 from './svgComponents/Cloud3'
import Cloud4 from './svgComponents/Cloud4'
import Cloud5 from './svgComponents/Cloud5'
import Mountains from './svgComponents/Mountains'
import Hills from './svgComponents/Hills'
// import Trees from './svgComponents/Trees'
// import WindTrail from './svgComponents/WindTrail'
import Ground from './svgComponents/Ground'
import Wave1 from './svgComponents/Wave1'
import Wave2 from './svgComponents/Wave2'
import Wave3 from './svgComponents/Wave3'

const layers = [
  { component: Cloud2, speed: 0.2 },
  { component: Cloud5, speed: 0.2 },
  { component: Cloud4, speed: 0.2 },
  { component: Mountains, speed: 0.3 },
  { component: Cloud1, speed: 0.3 },
  { component: Cloud3, speed: 0.3 },
  { component: Hills, speed: 0.6 },
  // { component: Trees, speed: 0.8 },
  // { component: WindTrail, speed: 0.7 },
  { component: Ground, speed: 0.9 },
  { component: Wave3, speed: 0.9 },
  { component: Wave2, speed: 0.92 },
  { component: Wave1, speed: 1 },
]

console.log(layers)

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
    Ground,
    Wave1,
    Wave2,
    Wave3,
  },
  data() {
    return {
      scrollY: 0,
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
  /* This container should stay fixed and centered on viewport resize */
  position: fixed;
  width: 2560px;
  height: 1000px;
  left: 50%;
  transform: translate(-50%, 0);
  background-color: #0087d5;
}

.foreground {
  position: absolute;
  top: 965px;
  left: 0;
  width: 100%;
  height: 100vh;
  background-color: #37559c;
  color: white;
}
</style>

<template>
  <div>
    <div class="parallax-container">
      <Cloud2 v-bind:style="{ transform: `translateY(${-scrollY * 0.2}px)`}" />
      <Cloud4 v-bind:style="{ transform: `translateY(${-scrollY * 0.3}px)`}" />
      <Cloud5 v-bind:style="{ transform: `translateY(${-scrollY * 0.2}px)`}" />
      <Mountains v-bind:style="{ transform: `translateY(${-scrollY * 0.3}px)`}" />
      <Cloud1 v-bind:style="{ transform: `translateY(${-scrollY * 0.3}px)`}" />
      <Cloud3 v-bind:style="{ transform: `translateY(${-scrollY * 0.3}px)`}" />
      <Hills v-bind:style="{ transform: `translateY(${-scrollY * 0.6}px)`}" />
      <Ground v-bind:style="{ transform: `translateY(${-scrollY * 0.9}px)`}" />
      <Wave3 v-bind:style="{ transform: `translateY(${-scrollY * 0.9}px)`}" />
      <Wave2 v-bind:style="{ transform: `translateY(${-scrollY * 0.92}px)`}" />
      <Wave1 v-bind:style="{ transform: `translateY(${-scrollY * 1}px)`}" />
    </div>
    <div class="foreground"></div>
  </div>
</template>
