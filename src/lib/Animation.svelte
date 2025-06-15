<script>
  const hexagonCount = 6;
</script>

<div class="hexagon-background">
  {#each Array(hexagonCount) as _, i}
    <div class="fakehexagon">
      <div class="face"></div>
      <div class="face"></div>
      <div class="face"></div>
    </div>
  {/each}
</div>

<style>
  .hexagon-background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    font-size: 100px;
    overflow: hidden;
    pointer-events: none;
    z-index: -1;
    display: flex;
    align-items: center;
    justify-content: center;
    -webkit-filter: drop-shadow(0 0 7px black) blur(10px) contrast(10);
    filter: drop-shadow(0 0 7px black) blur(10px) contrast(10);
  }

  .fakehexagon {
    position: absolute;
    width: 1em;
    height: 1em;
    top: 50%;
    left: 50%;
    margin: -0.5em 0 0 -0.5em;
    color: #fff;
  }

  .face {
    position: absolute;
    top: 0;
    left: 0;
    width: 1em;
    height: 1em;
    background: currentColor;
    transform-style: preserve-3d;
  }

  .face:nth-child(1) {
    transform: scale(1.4142) rotateX(-35deg) rotateY(-45deg) translateZ(0.5em);
  }

  .face:nth-child(2) {
    transform: scale(1.4142) rotateX(-35deg) rotateY(-45deg) translateX(0.5em) rotateY(90deg);
  }

  .face:nth-child(3) {
    transform: scale(1.4142) rotateX(-35deg) rotateY(-45deg) translateY(-0.5em) rotateX(90deg);
  }

  .face::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: currentColor;
    transform: translateZ(-1em);
  }

  /* Animations */

  @keyframes hex1 {
    from, 15% {
      transform: rotate(0deg) translateX(0) translateX(-1em) rotateY(0deg) translateX(1em);
    }
    65% {
      transform: rotate(0deg) translateX(2em) translateX(-1em) rotateY(0deg) translateX(1em);
    }
    to {
      transform: rotate(60deg) translateX(2em) translateX(-1em) rotateY(180deg) translateX(1em);
    }
  }

  @keyframes hex2 {
    from, 15% {
      transform: rotate(60deg) translateX(0) translateX(-1em) rotateY(0deg) translateX(1em);
    }
    65% {
      transform: rotate(60deg) translateX(2em) translateX(-1em) rotateY(0deg) translateX(1em);
    }
    to {
      transform: rotate(120deg) translateX(2em) translateX(-1em) rotateY(180deg) translateX(1em);
    }
  }

  @keyframes hex3 {
    from, 15% {
      transform: rotate(120deg) translateX(0) translateX(-1em) rotateY(0deg) translateX(1em);
    }
    65% {
      transform: rotate(120deg) translateX(2em) translateX(-1em) rotateY(0deg) translateX(1em);
    }
    to {
      transform: rotate(180deg) translateX(2em) translateX(-1em) rotateY(180deg) translateX(1em);
    }
  }

  @keyframes hex4 {
    from, 15% {
      transform: rotate(180deg) translateX(0) translateX(-1em) rotateY(0deg) translateX(1em);
    }
    65% {
      transform: rotate(180deg) translateX(2em) translateX(-1em) rotateY(0deg) translateX(1em);
    }
    to {
      transform: rotate(240deg) translateX(2em) translateX(-1em) rotateY(180deg) translateX(1em);
    }
  }

  @keyframes hex5 {
    from, 15% {
      transform: rotate(240deg) translateX(0) translateX(-1em) rotateY(0deg) translateX(1em);
    }
    65% {
      transform: rotate(240deg) translateX(2em) translateX(-1em) rotateY(0deg) translateX(1em);
    }
    to {
      transform: rotate(300deg) translateX(2em) translateX(-1em) rotateY(180deg) translateX(1em);
    }
  }

  @keyframes hex6 {
    from, 15% {
      transform: rotate(300deg) translateX(0) translateX(-1em) rotateY(0deg) translateX(1em);
    }
    65% {
      transform: rotate(300deg) translateX(2em) translateX(-1em) rotateY(0deg) translateX(1em);
    }
    to {
      transform: rotate(360deg) translateX(2em) translateX(-1em) rotateY(180deg) translateX(1em);
    }
  }

  .fakehexagon:nth-child(1) {
    color: hsl(0, 100%, 50%);
    animation: hex1 4.5s infinite;
  }
  .fakehexagon:nth-child(2) {
    color: hsl(60, 100%, 50%);
    animation: hex2 4.5s infinite;
  }
  .fakehexagon:nth-child(3) {
    color: hsl(120, 100%, 50%);
    animation: hex3 4.5s infinite;
  }
  .fakehexagon:nth-child(4) {
    color: hsl(180, 100%, 50%);
    animation: hex4 4.5s infinite;
  }
  .fakehexagon:nth-child(5) {
    color: hsl(240, 100%, 50%);
    animation: hex5 4.5s infinite;
  }
  .fakehexagon:nth-child(6) {
    color: hsl(300, 100%, 50%);
    animation: hex6 4.5s infinite;
  }
</style>
