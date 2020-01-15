<style lang="scss">
  .color-block_swatch {
    background-color: var(--color-swatch);
    position: relative;
    width: 100%;
    transform: scale(1);
    transition: transform ease-in 0.1s;
    border-radius: 10px;
    border: 2px solid var(--background-color);
    &:focus {
      outline: 0;
      box-shadow: 0 0 0 2px var(--foreground-color);
    }
    &:after {
      content: "";
      display: block;
      padding-bottom: 100%;
    }
  }
  .color-block_name {
    display: none;
  }
  .copy-animate {
    display: block;
    transform: scale(0.9);
  }
</style>

<template>
  <div class="color-block">
    <div class="color-block_swatch" v-bind:style="`--color-swatch: ${value};`" v-bind:title="`${name}`" v-on:click="colorCopy(value), animateButton($event)" tabindex="0">
    </div>
    <p class="color-block_name">{{ name }}<br><small>{{ value }}</small></p>
  </div>
</template>

<script>
  export default {
    name: 'colorBlock',
    props: ['name', 'value'],
    methods: {
      colorCopy: function (color) {
        const {clipboard} = require('electron')
        clipboard.writeText(color, 'selection')
        console.log('coppied:', color)
      },
      animateButton: function (event) {
        let e = event.currentTarget
        // e.preventDefault; I'm not sure why this is necessary
        e.classList.remove('copy-animate')
        e.classList.add('copy-animate')
        setTimeout(function () {
          e.classList.remove('copy-animate')
        }, 100)
      }
    }
  }
</script>
