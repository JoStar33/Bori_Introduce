<template>
  <div class="🐕">
    <div class="torso">
      <div class="fur">
        <div class="spot"></div>
      </div>
      <div class="neck">
        <div class="fur"></div>
        <div class="head">
          <div class="fur">
            <div class="snout"></div>          
          </div>
          <div class="ears">
            <div class="ear">
              <div class="fur"></div>
            </div>
            <div class="ear">
              <div class="fur"></div>
            </div>
          </div>
          <div class="eye"></div>
        </div>
        <div class="collar">
          
        </div>
      </div>
      <div class="legs">
        <div class="leg">
          <div class="fur"></div>
          <div class="leg-inner">
            <div class="fur"></div>
          </div>
        </div>
        <div class="leg">
          <div class="fur"></div>
          <div class="leg-inner">
            <div class="fur"></div>
          </div>
        </div>
        <div class="leg">
          <div class="fur"></div>
          <div class="leg-inner">
            <div class="fur"></div>
          </div>
        </div>
        <div class="leg">
          <div class="fur"></div>
          <div class="leg-inner">
            <div class="fur"></div>
          </div>
        </div>
      </div>
      <div class="tail">
        <div class="tail">
          <div class="tail">
            <div class="tail -end">
              <div class="tail">
                <div class="tail">
                  <div class="tail">
                    <div class="tail"></div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss">
  :root {
    --color-fur: #ffb141;
    --color-fur-dark: #F5832C;
    --color-spot: #F9584C;
    --color-snout: #544258;
    --color-collar: #3EAB6C;
    --duration: .7s;
    --semi-duration: calc(var(--duration) / 2);
    --easing: cubic-bezier(.5, 0, .5, 1);
    --stagger: calc(-1 * var(--semi-duration) / 2);
  }

  *, *:before, *:after {
    animation-timing-function: var(--easing) !important ;
  }

  [class="🐕"] {
    z-index: 1;
    height: 300px;
    width: 300px;
    display: flex;
    justify-content: center;
    align-items: center;
    
    * {
      position: absolute;
      will-change: transform;
    }
    
    &:before {
      content: '';
      position: absolute;
      bottom: percentage(40px / 300px);
      left: 0;
      width: 100%;
      height: percentage(10px / 300px);
      background-color: #D3D1D1;
      border-radius: 2px;
      animation: shadow
        calc(1 * var(--semi-duration))
        infinite;
      
      @keyframes shadow {
        from, to {
          transform: scaleX(.75)
        }
        45%, 55% {
          transform: scaleX(.5)
        }
      }
    }
  }

  .neck {
    width: 50%;
    height: 100px;
    right: -5px;
    bottom: calc(100% - 10px);
    transform-origin: center bottom;
    transform: rotate(15deg);
    z-index: 2;
    
    > .fur {
      border-bottom-left-radius: 10px;
      height: 100%;
      width: 100%;
      
      &:before {
        content: '';
        position: absolute;
        top: 0;
        right: 0;
        height: 50px;
        width: 100%;
        background-color: var(--color-fur-dark);
        z-index: 1;
        transform-origin: right bottom;
        transform: rotate(15deg);
      }
    }
  }

  .collar {
    width: calc(100% + 10px);
    height: 15%;
    background-color: var(--color-collar);
    left: -5px;
    bottom: 30px;
    border-radius: 5px;
    animation: collar var(--semi-duration) calc(var(--semi-duration) / 4) infinite;
    z-index: 2;
    
    @keyframes collar {
      from, to {
        transform: none;
      }
      50% {
        transform: translateY(-25%);
      }
    }
    
    &:after {
      content: '';
      width: 18%;
      height: 120%;
      border-radius: 50%;
      background: var(--color-snout);
      position: absolute;
      right: 0%;
      top: 110%;
      transform-origin: center top;
      animation: tag var(--semi-duration) infinite both;
      
      @keyframes tag {
        from, to {
          transform: rotate(-15deg);
        }
        50% {
          transform: rotate(-15deg) scaleY(1.5);
        }
      }
    }
  }

  .head {
    height: 80%;
    width: 145%;
    left: -2%;
    bottom: 50%;
    transform-origin: left center;
    z-index: 2;
    animation: head var(--semi-duration) calc(var(--semi-duration) / 4) infinite;
    
    @keyframes head {
      from, to {
        transform: rotate(-10deg);
      }
      50% {
        transform: rotate(-15deg);
      }
    }
    
    > .fur {
      height: 100%;
      width: 100%;
      border-bottom-right-radius: 80px;
      
      &:before {
        content: '';
        position: absolute;
        top: -80%;
        left: -30%;
        width: 100%;
        height: 0;
        padding-top: 100%;
        background-color: var(--color-spot);
        z-index: 1;
        border-radius: 50%;
      }
    }
  }

  .snout {
    --color: var(--color-snout);
    width: 25%;
    height: 0;
    padding-top: 25%;
    background-color: var(--color);
    top: 0;
    right: -5px;
    border-bottom-left-radius: 100%;
    z-index: 1;
  }

  .ears {
    bottom: 40%;
    height: 100%;
    width: 30%;
    left: 0;
    z-index: -1;
  }

  .ear {
    --color: var(--color-spot);
    width: 100%;
    height: 100%;
    bottom: 0;
    left: 0;
    transform-origin: left bottom;
    transform: rotate(-10deg);
    animation: ear-front calc(var(--duration) / 2) infinite;
    
    @keyframes ear-front {
      50% {
        transform: rotate(-15deg);
      }
    }
    
      &:before {
        content: '';
        position: absolute;
        height: 25px;
        width: 15px;
        z-index: 2;
        top: -2px;
        right: -7px;
        border-top-left-radius: 100%;
        border-width: 2px;
        border-color: transparent;
        border-style: solid;
        border-left: 2px solid var(--color-snout);
        transform-origin: bottom left;
        animation: ear-mark var(--semi-duration) calc(-1 * var(--semi-duration)) infinite;
        
        @keyframes ear-mark {
          from, to {
            transform: rotate(0deg);
          }
          50% {
            transform: rotate(25deg);
          }
        }
      }
    
    > .fur {
      border-top-left-radius: 100%;
      height: 100%;
      width: 100%;
    }
    
    &:nth-child(2) {
      left: 15px;
      bottom: 5px;
      transform: rotate(-5deg);
      --color: var(--color-fur);
      z-index: -1;
      animation: ear-back calc(var(--duration) / 2) infinite both;
      
      @keyframes ear-back {
        from, to {
          transform: rotate(0deg);
        }
        50% {
          transform: rotate(-10deg);
        }
      }
    }
  }

  .eye {
    --size: 6%;
    --color: var(--color-snout);
    width: var(--size);
    height: 0;
    padding: var(--size);
    left: 35%;
    top: 20%;
    border-radius: 50%;
    background-color: var(--color);
    z-index: 1;
    
    &:before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      border-radius: 50%;
      background-color: var(--color);
      z-index: 1;
    }
    
    &:after {
      content: '';
      width: 100%;
      height: 100%;
      position: absolute;
      left: -50%;
      top: -50%;
      border-top-left-radius: 100%;
      border-width: 2px;
      border-color: var(--color);
      border-style: solid;
      border-bottom-color: var(--color-spot);
      border-right-color: var(--color-spot);
      transform: scale(1.25);
      z-index: 0;
    }
  }

  .torso {
    width: percentage(170px / 300px);
    height: percentage(100px / 300px);
    animation: torso var(--semi-duration) both infinite;
    
    @keyframes torso {
      from, to {
        transform: none;
      }
      50% {
        transform: translateY(15%);
      }
    }
    
    > .fur {
      height: 100%;
      width: 185px;
      border-top-left-radius: 40px;
      transform-origin: left center;
      transform: rotate(-20deg) translateY(10px);
      z-index: 1;
      
      &:after {
        height: 100%;
        width: 100%;
        border-bottom-left-radius: 200px 85px;
        border-bottom-right-radius: 100px;
      }
    }
    
    > .legs {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
    }
    
    .spot {
      width: 120px;
      height: 120px;
      bottom: 40px;
      left: -20px;
      border-radius: 50%;
      background-color: var(--color-spot);
      z-index: 1;
      animation: spot var(--duration) calc(-1 * var(--semi-duration)) both infinite;
      
      @keyframes spot {
        from, 66%, to {
          transform: none;
        }
        33% {
          transform: translateX(10px);
        }
      }
      
      &:after {
        content: '';
        height: 20px;
        width: 20px;
        border-radius: 50%;
        background-color: inherit;
        position: absolute;
        bottom: -10px;
        right: 5px;
      }
    }
    
    > .tail {
      --color: var(--color-spot);
      bottom: calc(100% - 15px);
      left: 0;
      transform-origin: center bottom;
      transform: rotate(-45deg);
    }
  }

  .tail {
    height: 15px;
    width: 20px;
    background-color: var(--color);
    border-top-right-radius: 10px 100%;
    border-top-left-radius: 10px 100%;
    animation: tail var(--semi-duration) infinite;
    
    @keyframes tail {
      from, to {
        transform: rotate(-45deg) translateX(-15%);
      }
      50% {
        transform: rotate(-25deg) translateX(15%);
      }
    }
    
    > .tail {
      bottom: calc(90%);
      transform-origin: bottom left;
      transform: rotate(-10deg) translateY(50%) scaleX(.8) scaleY(.9);
      animation: tail-inner var(--semi-duration) var(--stagger) infinite;
      
      @keyframes tail-inner {
        from, to {
          transform: rotate(-10deg) translateY(50%) scaleX(.8) scaleY(.9);
        }
        50% {
          transform: rotate(5deg) translateY(50%) scaleX(.8) scaleY(.9)
        }
      }
    }
  }

  .legs {
    > .leg {
      bottom: 5px;
      --color: var(--color-fur);
    }
    
    > .leg:nth-child(1), .leg:nth-child(3) {
      // top: calc(100% - 65px);
      right: 15px;
    }
    
    > .leg:nth-child(3), > .leg:nth-child(4) {
      --color: var(--color-fur-dark);
      z-index: -1;
    }
    
    > .leg:nth-child(1), .leg:nth-child(4) {
      --delay: 0s;
    }
    
    > .leg:nth-child(2), > .leg:nth-child(3) {
      --delay: calc(-1 * var(--duration) / 2 )
    }
    
    > .leg:nth-child(2) {
      left: 0;
    }
    
    > .leg:nth-child(4) {
      left: 0;
    }

  }

  .leg {
    position: absolute;
    height: 65px;
    width: 45px;
    background-color: var(--color);
    transform-origin: center 5px;
    // transform: rotate(-10deg);
    // border-bottom-right-radius: 10px;
    animation: leg infinite var(--duration) var(--delay, 0s);
    
    > .leg-inner {
      animation: leg-inner infinite
        var(--duration)
        calc(var(--delay));
      transform: rotate(90deg);
      
      @keyframes leg-inner {
        from, to {
          transform: none;
        }
        33% {
          transform: rotate(70deg);
        }
        76% {
          transform: none;
        }
      }
    }
    
    @keyframes leg {
      from, to {
        transform: none;
      }
      33% {
        transform: rotate(-55deg);
      }
      66% {
        transform: rotate(-20deg);
      }
    }

    > .fur {
      width: percentage(65px / 45px);
      height: 100%;

      &:after {
        width: 45px;
        bottom: 0;
        top: initial;
        transform: rotate(15deg);
        // height: 100%;
      }
    }
  }

  .fur {
    position: absolute;
    overflow: hidden;

    &:after {
      content: "";
      position: absolute;
      width: 100%;
      height: 150%;
      top: 0;
      left: 0;
      background-color: var(--color, var(--color-fur));
      transform-origin: center bottom;
    }
  }

  .leg-inner {
    position: absolute;
    height: 65%;
    width: 100%;
    // background-color: #FFB141;
    top: calc(100%);
    transform-origin: center top;

    &:before {
      // joint
      content: "";
      width: 45px;
      height: 45px;
      background-color: var(--color);
      // background-color: blue;
      position: absolute;
      border-radius: 50%;
      top: -22.5px;
      left: -0.5px;
    }

    > .fur {
      width: 100%;
      height: 100%;

      position: absolute;
      top: 0;
      left: 0;
      overflow: hidden;

      &:after {
        content: "";
        position: absolute;
        width: 100%;
        height: 170%;
        top: 0;
        left: 0;
        background-color: var(--color);
        transform-origin: center top;
        transform: rotate(15deg);
      }
    }
  }

  *,
  *:before,
  *:after {
    box-sizing: border-box;
    position: relative;
  }

</style>