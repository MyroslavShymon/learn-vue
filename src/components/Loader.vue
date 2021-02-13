<template>
  <div class="lds-roller">
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
  </div>
</template>

<style lang="scss" scoped>
.lds-roller {
  margin: 100px 0 0 0;
  display: inline-block;
  position: relative;
  width: 80px;
  height: 80px;
  div {
    animation: lds-roller 1.2s cubic-bezier(0.5, 0, 0.5, 1) infinite;
    transform-origin: 40px 40px;
    &::after {
      content: " ";
      display: block;
      position: absolute;
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: #fff;
      margin: -4px 0 0 -4px;
    }
    @for $i from 1 through 8 {
      &:nth-child(#{$i}) {
        animation-delay: -0.036s * $i;
        &::after {
          top: $i * $i * -1 + 8 * $i + 56;
          left: 0.0758 * $i * $i * $i - 0.8918 * $i * $i - 4.8009 * $i + 68.571;
        }
      }
    }
  }
}
@keyframes lds-roller {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
