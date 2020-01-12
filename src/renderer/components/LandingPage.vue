<template>
  <div id="wrapper">
    <h1>Color Palettes</h1>
    <section v-for="palette in palettes" v-bind:key="palette.id">
      <h2>{{ palette.title }}</h2>
      <div class="grid">
        <color-block v-for="color in palette.colors" v-bind:name="color.name" v-bind:value="color.value" v-bind:key="color.id"></color-block>
      </div>
    </section>
  </div>
</template>

<script>
  import colorBlock from './LandingPage/ColorBlock.vue'

  export default {
    name: 'landing-page',
    components: { colorBlock },
    methods: {
      open (link) {
        this.$electron.shell.openExternal(link)
      }
    },
    data () {
      return {
        palettes: [
          {
            title: 'Personal Brand',
            colors: [
              {name: 'Haze', value: '#f7f7f7'},
              {name: 'Turquoise', value: '#4ecdc4'},
              {name: 'Summer Sky', value: '#1ea8d1'},
              {name: 'Midnight', value: '#294159'},
              {name: 'Dusk', value: '#4f6f8e'}
            ]
          },
          {
            title: 'UAB',
            colors: [
              {name: 'UAB Green', value: '#1E6B52'},
              {name: 'Dark Green', value: '#295135'},
              {name: 'Apple', value: '#80bc00'},
              {name: 'Blaze', value: '#ffd400'},
              {name: 'Gold', value: '#aa9767'},
              {name: 'Stone', value: '#808285'}
            ]
          }
        ]
      }
    }
  }
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css?family=Source+Sans+Pro');

  // 18px base font size
  html {font-size: 112.5%;}
  p {margin-bottom: 1.15rem;}
  h1, h2, h3, h4, h5 {
    margin: 2.75rem 0 1.05rem;
    line-height: 1.15;
  }
  h1 {
    margin-top: 0;
    font-size: 3.052em;
  }
  h2 {font-size: 2.441em;}
  h3 {font-size: 1.953em;}
  h4 {font-size: 1.563em;}
  h5 {font-size: 1.25em;}
  small, .text_small {font-size: 0.8em;}

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: 'Source Sans Pro', sans-serif;
    color: #424242;
    padding: 3.052em;
  }

  .grid {
    display: grid;
    grid-gap: 1.15rem;
    grid-template-columns: repeat( auto-fill, minmax(100px, 1fr) );
  }
</style>
