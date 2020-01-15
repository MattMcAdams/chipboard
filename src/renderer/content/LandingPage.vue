<style lang="scss">
  @import url('https://fonts.googleapis.com/css?family=Source+Sans+Pro');
  :root {
    --foreground-color: #242424;
    --background-color: white;
  }
  // 18px base font size
  //html {font-size: 112.5%;}
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
    color: var(--foreground-color);
    padding: 1.5em;
    background-color: var(--background-color);
  }
</style>

<template>
  <div id="wrapper">
    <section v-for="palette in palettes" v-bind:key="palette.id">
      <color-palette v-bind:palette="palette"></color-palette>
    </section>
  </div>
</template>

<script>
  import colorPalette from './components/ColorPalette.vue'

  export default {
    name: 'landing-page',
    components: { colorPalette },
    methods: {
      open (link) {
        this.$electron.shell.openExternal(link)
      }
    },
    data () {
      return {
        palettes: [
          {
            title: 'UAB Standard',
            colors: [
              {name: 'UAB Green', value: '#1E6B52'},
              {name: 'Dark Green', value: '#295135'},
              {name: 'Apple', value: '#80bc00'},
              {name: 'Blaze', value: '#ffd400'},
              {name: 'Gold', value: '#aa9767'},
              {name: 'Stone', value: '#808285'}
            ]
          },
          {
            title: 'Primary',
            colors: [
              {name: 'Primary 900', value: '#061510'},
              {name: 'Primary 800', value: '#0c2b21'},
              {name: 'Primary 700', value: '#124031'},
              {name: 'Primary 600', value: '#185642'},
              {name: 'Primary 500', value: '#1e6b52'},
              {name: 'Primary 400', value: '#4b8975'},
              {name: 'Primary 300', value: '#78a697'},
              {name: 'Primary 200', value: '#a5c4ba'},
              {name: 'Primary 100', value: '#d2e1dc'}
            ]
          },
          {
            title: 'Accent',
            colors: [
              {name: 'Accent 900', value: '#1a2600'},
              {name: 'Accent 800', value: '#334b00'},
              {name: 'Accent 700', value: '#4d7100'},
              {name: 'Accent 600', value: '#669600'},
              {name: 'Accent 500', value: '#80bc00'},
              {name: 'Accent 400', value: '#99c933'},
              {name: 'Accent 300', value: '#b3d766'},
              {name: 'Accent 200', value: '#cce499'},
              {name: 'Accent 100', value: '#e6f2cc'}
            ]
          },
          {
            title: 'Secondary',
            colors: [
              {name: 'Secondary 900', value: '#08100b'},
              {name: 'Secondary 800', value: '#102015'},
              {name: 'Secondary 700', value: '#193120'},
              {name: 'Secondary 600', value: '#21412a'},
              {name: 'Secondary 500', value: '#295a35'},
              {name: 'Secondary 400', value: '#54745d'},
              {name: 'Secondary 300', value: '#7f9786'},
              {name: 'Secondary 200', value: '#a9b9ae'},
              {name: 'Secondary 100', value: '#d4dcd7'}
            ]
          },
          {
            title: 'Neutral',
            colors: [
              {name: 'Neutral 900', value: '#1a1a1b'},
              {name: 'Neutral 800', value: '#333435'},
              {name: 'Neutral 700', value: '#4d4e50'},
              {name: 'Neutral 600', value: '#66686a'},
              {name: 'Neutral 500', value: '#808285'},
              {name: 'Neutral 400', value: '#999b9d'},
              {name: 'Neutral 300', value: '#b3b4b6'},
              {name: 'Neutral 200', value: '#cccdce'},
              {name: 'Neutral 100', value: '#e6e6e7'}
            ]
          },
          {
            title: 'Caution',
            colors: [
              {name: 'Caution 900', value: '#332a00'},
              {name: 'Caution 800', value: '#665500'},
              {name: 'Caution 700', value: '#997f00'},
              {name: 'Caution 600', value: '#ccaa00'},
              {name: 'Caution 500', value: '#ffd400'},
              {name: 'Caution 400', value: '#ffdd33'},
              {name: 'Caution 300', value: '#ffe566'},
              {name: 'Caution 200', value: '#ffee99'},
              {name: 'Caution 100', value: '#fff6cc'}
            ]
          },
          {
            title: 'Caution Alt',
            colors: [
              {name: 'Caution-alt 900', value: '#331e00'},
              {name: 'Caution-alt 800', value: '#663d00'},
              {name: 'Caution-alt 700', value: '#995b00'},
              {name: 'Caution-alt 600', value: '#cc7a00'},
              {name: 'Caution-alt 500', value: '#ff9800'},
              {name: 'Caution-alt 400', value: '#ffad33'},
              {name: 'Caution-alt 300', value: '#ffc166'},
              {name: 'Caution-alt 200', value: '#ffd699'},
              {name: 'Caution-alt 100', value: '#ffeacc'}
            ]
          },
          {
            title: 'Warning',
            colors: [
              {name: 'warning 900', value: '#330000'},
              {name: 'warning 800', value: '#660000'},
              {name: 'warning 700', value: '#990000'},
              {name: 'warning 600', value: '#cc0000'},
              {name: 'warning 500', value: '#ff0000'},
              {name: 'warning 400', value: '#ff3333'},
              {name: 'warning 300', value: '#ff6666'},
              {name: 'warning 200', value: '#ff9999'},
              {name: 'warning 100', value: '#ffcccc'}
            ]
          }
        ]
      }
    }
  }
</script>
