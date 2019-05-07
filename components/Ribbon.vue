<template>
  <v-layout xs12 class="ribbon">
    <v-flex text-xs-center>
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
  min-height: 48px;
  background-color: #00dcb4;
  position: absolute;
  top: 0;
  left: 0;
  justify-content: center;
  align-items: center;
  padding: 0 24px;
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
  &__text {
    font-size: 18px;
  }
}
</style>
