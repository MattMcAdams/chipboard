<style lang="scss">
  .grid {
    display: grid;
    grid-gap: 0.5rem;
    grid-template-columns: repeat( auto-fill, minmax(50px, 1fr) );
  }
</style>

<template>
  <section>
    <h2>{{ palette.title }}</h2>
    <div class="grid">
      <color-block v-for="color in palette.colors" v-bind:name="color.name" v-bind:value="color.value" v-bind:key="color.id"></color-block>
    </div>
  </section>
</template>

<script>
  import colorBlock from './ColorBlock.vue'

  export default {
    name: 'color-palette',
    components: { colorBlock },
    props: ['palette']
  }
</script>
