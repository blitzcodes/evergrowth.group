<template>
  <article class="p-home">
    <section class="p-home__content">
      <header>
        <Logo/>
        <h1>Evergrowth</h1>
        <h2>Mastermind</h2>
      </header>
      <!--<AniText text="Learn, Evolve, Always."></AniText>-->
      <div class="o-card__list">
        <div class="o-card informational" style="display: none !important;">
          <div>
            <span class="o-card__date">Upcoming Talk</span>
            <p style="margin-top: 0;">Saturday June 8, 2019 at 10am - 1pm EST</p>
            <h3 class="o-card__title">Are you a high performer, or just a workaholic?</h3>
            <div class="o-card__desc">
              We will be exploring a polarizing topic as we breakdown what it means to be a high performer, in life and professionally. We'll also be looking at where that line gets crossed, and the consequences that result from it. It's sure to be an enticing talk without a doubt.
              <br><br>
              <b>We look forward to having you join us.</b> Or, have a listen! <a
              href="https://www.twitch.tv/evergrowthmastermind" target="_blank">Join the audio stream on Twitch</a> on the 8th at 10:30am to catch it live.
            </div>
          </div>
        </div>
        <div class="o-card" v-for="entry in recordings">
          <div>
            <span class="o-card__date" v-html="entry.date"></span>
            <h3 class="o-card__title" v-html="entry.title"></h3>
            <div class="o-card__desc" v-html="entry.desc"></div>
          </div>
          <div class="o-card__audio" v-html="entry.audio"></div>
        </div>
      </div>
    </section>
  </article>
</template>

<script>
  import Logo from './Logo';
  import AniText from './AniText';
  import Player from './Player';

  export default {
    name: 'p-home',
    components: {
      Logo,
      AniText,
      Player,
    },
    data() {
      return {
        recordings: [
          {
            title: 'Are you a high-achiever, or just a workaholic?',
            date: 'June 2019 - Playback',
            desc: `We explored a polarizing topic as we broke down what it means to be a high-achiever, in life and professionally, and when you may instead have become a workaholic. We'll also be looked at where that line gets crossed, and the consequences that result from it. It was an enticing talk without a doubt.<br><br>Enjoy!`,
            audio: '<iframe width="100%" height="300" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/634179216&color=%23ff5500&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true&visual=true"></iframe>',
          },
        ],
      };
    },
  };
</script>

<style lang="scss">
  $c-brand-green: rgb(53, 183, 41);

  .p-home {
    display: flex;
    justify-items: center;
    align-items: center;
    width: 100vw;
    margin-top: 2rem;

    a {
      color: white;
    }

    header {
      padding: 1rem;
      border-radius: 100%;
      width: 300px;
      height: 200px;
      margin: 0 auto 1rem;
    }
  }

  .p-home__content {
    margin: 0 auto;
    text-align: center;
    max-width: 90%
  }

  h1,
  h2 {
    text-transform: uppercase;
    margin: 0;
    font-family: 'Roboto Condensed', sans-serif;
  }

  h1 {
    font-size: 2.5rem;
    margin-top: .5rem;
  }

  h2 {
    font-size: 1.75rem;
    margin-bottom: 1rem;
  }

  .o-card__list {
    /*display: flex;*/
    /*flex-wrap: wrap;*/
    /*justify-content: center;*/
  }

  .o-card {
    padding: 1rem;
    background: rgba(74, 102, 118, 0.6);
    border-radius: 5px;
    text-align: left;
    width: 600px;
    max-width: 93%;
    margin-bottom: 2rem;

    @media (min-width: 640px) {
      display: flex;
    }

    > div:nth-child(1) {
      margin-bottom: 2rem;

      @media (min-width: 640px) {
        flex: 0 0 45%;
        padding-right: 5%;
        margin: 0;
      }
    }

    &.informational > div:nth-child(1) {
      margin: 0 !important;
      flex: 0 0 100% !important;
      padding: 0 !important;
    }

    > div:nth-child(2) {
      flex: 0 0 50%;
    }


    h3 {
      margin-top: 0;
    }

    .o-card__date {
      text-transform: uppercase;
      font-size: 1rem;
    }

    .o-card__title {
      font-size: 1.5rem;
      text-transform: uppercase;
    }

    .o-card__desc {
      font-size: 1.15rem;
      line-height: 1.5;
    }

    .o-card__audio {
      @media (min-width: 640px) {
        margin-top: 1rem;
      }
    }

    iframe {
      max-width: 100%;
    }
  }
</style>
<!-- Add "scoped" attribute to limit CSS to this component only -->
