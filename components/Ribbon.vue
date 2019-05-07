<template>
  <v-layout class="ribbon">
    <v-flex text-xs-center xs12 lg4 class="ribbon__content">
      <span class="ribbon__text"><strong>100% online –</strong> Short courses &amp; degrees</span>
    </v-flex>
  </v-layout>
</template>

<script>
  export default {

  }
</script>

<style lang="scss">
.ribbon {
  justify-content: center;
  align-items: center;
  &__content {
    min-height: 48px;
    background-color: #00dcb4;
    position: absolute;
    top: 0;
    left: 0;
    justify-content: center;
    align-items: center;
    padding: 0 24px;
    width: 100%;
    line-height: 48px;
    &:after {
      display: block;
      content: '';
      position: absolute;
      width: 48px;
      height: 100%;
      right: -48px;
      top: 0;
      border-top: 48px solid #00dcb4;
      border-right: 48px solid transparent;
    }
  }
  &__text {
    font-size: 18px;
  }
}
</style>
