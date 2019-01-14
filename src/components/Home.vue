<template>
  <article class="p-home">
    <section class="p-home__content">
      <Logo/>
      <h1>Evergrowth</h1>
      <h2>Mastermind</h2>
      <AniText text="Learn, Evolve, Always."></AniText>
    </section>
  </article>
</template>

<script>
  import Logo from './Logo'
  import AniText from './AniText'

  export default {
    name: 'p-home',
    components: {
      Logo,
      AniText,
    },
    data () {
      return {}
    },
  }
</script>

<style lang="scss">
  $c-brand-green: rgb(53, 183, 41);

  .p-home {
    display: flex;
    justify-items: center;
    align-items: center;

    background: $c-brand-green;
    height: 100vh;
    width: 100vw;
  }

  .p-home__content {
    margin: 0 auto;
    text-align: center;
  }

  h1,
  h2 {
    text-transform: uppercase;
    margin: 0;
    font-family: 'Roboto Condensed', sans-serif;
  }

  h1 {
    font-size: 4rem;
    margin-top: .5rem;
  }

  h2 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
  }
</style>
<!-- Add "scoped" attribute to limit CSS to this component only -->
