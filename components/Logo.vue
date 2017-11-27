<template>
  <!-- <div class="VueToNuxtLogo">
    <div class="Triangle Triangle--two"></div>
    <div class="Triangle Triangle--one"></div>
    <div class="Triangle Triangle--three"></div>
    <div class="Triangle Triangle--four"></div>
  </div> -->
  <div id="svg-container" class="svg-container">
    <svg version="1.1" id="al-logo" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
       viewBox="0 0 400 400" enable-background="new 0 0 400 400" xml:space="preserve">
    <g id="Layer_4">
      <g id="circle-container">
        <circle id="circle" fill="#2c3e50" cx="200" cy="200" r="180"/>
        <path id="letter" fill="#FFFFFF" d="M166.8,237.7h-16.9l44.2-85.3h11.8l44.1,85.3h-16.9l-8.5-16.2h-49.3 M216.9,207.1l-17.1-32.6l-17,32.6
        H216.9z"/>
      </g>
      <path id="blue-bracket" fill="#00BCD4" d="M271.9,124.6c2.6,0.3,3.9,2.7,4.2,5.2L311,293.7v-198c0-3.9-2.2-7.1-6-7.1l-199.2,0L271.9,124.6z"/>
      <path id="white-bracket" fill="#FFFFFF" d="M125.9,276.9c-2.6-0.3-4.8-2.9-5.1-5.4L86,107.6v198c0,3.9,3.1,7.1,7,7.1l198.1,0L125.9,276.9z"/>

    </g>
    <g id="Layer_7" display="none">
      <path display="inline"  fill="#FFFFFF" d="M166.8,237.7h-16.9l44.2-85.3h11.8l44.1,85.3h-16.9l-8.5-16.2h-49.3 M216.9,207.1
        l-17.1-32.6l-17,32.6H216.9z"/>
    </g>
    </svg>
  </div>
</template>

<style>
.svg-container {
  transition: transform 0.4s ease;
  width:30px;
  height: 30px;
}

/*@media screen and (min-width: 1023px) {
  .svg-container {
    transform: scale3d(2, 2, 4) translate3d(10px, 15px, 0);
  }
}

.headroom.headroom--not-top .svg-container {
  transform: scale3d(1,1,1);
}*/

.VueToNuxtLogo {
  display: inline-block;
  animation: turn 2s linear forwards 1s;
  transform: rotateX(180deg);
  position: relative;
  overflow: hidden;
  height: 180px;
  width: 245px;
}


.Triangle {
  position: absolute;
  top: 0;
  left: 0;
  width: 0;
  height: 0;
}

.Triangle--one {
  border-left: 105px solid transparent;
  border-right: 105px solid transparent;
  border-bottom: 180px solid #41B883;
}

.Triangle--two {
  top: 30px;
  left: 35px;
  animation: goright 0.5s linear forwards 3.5s;
  border-left: 87.5px solid transparent;
  border-right: 87.5px solid transparent;
  border-bottom: 150px solid #3B8070;
}

.Triangle--three {
  top: 60px;
  left: 35px;
  animation: goright 0.5s linear forwards 3.5s;
  border-left: 70px solid transparent;
  border-right: 70px solid transparent;
  border-bottom: 120px solid #35495E;
}

.Triangle--four {
  top: 120px;
  left: 70px;
  animation: godown 0.5s linear forwards 3s;
  border-left: 35px solid transparent;
  border-right: 35px solid transparent;
  border-bottom: 60px solid #fff;
}

@keyframes turn {
  100% {
    transform: rotateX(0deg);
  }
}

@keyframes godown {
  100% {
    top: 180px;
  }
}

@keyframes goright {
  100% {
    left: 70px;
  }
}
</style>
