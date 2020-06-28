<template>
  <svg>
    <filter id="seaFloorFilter" x="0" y="0" width="100%" height="100%">
      <feTurbulence id="seaFloorWaves" numOctaves="1" seed="2" baseFrequency="0.02 0.05" />
      <feDisplacementMap scale="10" in="SourceGraphic" />
      <animate
        xlink:href="#seaFloorWaves"
        attributeName="baseFrequency"
        dur="60s"
        keyTimes="0;0.5;1"
        values="0.01 0.06;0.02 0.09;0.01 0.06"
        repeatCount="indefinite"
      />
    </filter>
  </svg>
</template>