# SVG Parallax Fjord - Built with Vue

https://vue.parallaxfjord.com/

My first attempt at this site was built with React. This is my 3rd time building it, and this time with Vue. This rebuild was partly for practice and partle to have something to benchmark and compare bundle sizes in multiple platforms.

## Some cool things about the project

- No animation library added for Parallax effects. It uses a simple scroll handler and v-bind to style all parallax layers on the page with a `scrollY` variable, as well as the background transition.
- ~~Uses CSS variables from a derived value to accomplish background transition.~~
  - I have since learned that CSS variables do not perform well when being recalculated, particularly when the element it is declared on has a lot of children. I've switched this to simple js variables that are read on the element for better performance
- Built for up to 2560px resolution.
- SVG morphing animations for trees blowing in the wind using snap-svg.
