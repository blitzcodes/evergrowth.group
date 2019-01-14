<template>
  <p class="a-anitext">
    {{ text }}
  </p>
</template>

<script>
  // import '@/lib/splitText'
  import { TimelineMax, TweenLite, Power2 } from 'gsap'

  export default {
    name: 'AniText',
    props: {
      text: String,
    },
    mounted: function () {
      const quote = this.$el
      // const mySplitText = new SplitText(quote, { type: 'words' })
      const tl = new TimelineMax({
        delay: 1,
        repeat: 10,
        repeatDelay: 1,
      })
      // let numWords = mySplitText.words.length

      //prep the quote div for 3D goodness
      TweenLite.set(quote, {
        transformPerspective: 600,
        perspective: 300,
        transformStyle: 'preserve-3d',
        autoAlpha: 1,
      })

      tl.from(quote, tl.duration(), { rotationY: 180, transformOrigin: '50% 75% 200', ease: Power2.easeOut }, 0)
    },
  }
</script>

<style lang="scss">
  .a-anitext {
    font-size: 2rem;
    /*transform: translate3d(0, 0, 0);*/
    /*line-height: 36px;*/
    color: #fff;
    /*margin: 50px auto;*/
    /*width: 800px;*/
    /*visibility: hidden;*/
    text-shadow: 3px 3px 2px rgba(0, 0, 0, .333);

    @media screen and (max-width: 640px) {
      font-size: 1.5rem;
    }

    div {
      -webkit-font-smoothing: antialiased;
      -moz-font-smoothing: antialiased;
    }
  }
</style>
