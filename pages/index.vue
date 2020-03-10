<template>
  <main>
    <div class="front">
      <div class="front__titles">
        <div class="front__titles__sub">
          Welcome To Our Studio!
        </div>
        <div class="front__titles__main">
          IT'S NICE TO MEET YOU
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import axios from 'axios'

export default {
  head() {
    return {
      meta: [
        {
          hid: 'kozikozi',
          name: 'kozi~mon~',
          content: 'kozimon! kozimon!'
        }
      ]
    }
  },
  head: {
    link: [
      {
        rel: 'stylesheet',
        href:
          'https://fonts.googleapis.com/css?family=Droid+Serif:400,700,400italic,700italic'
      }
    ]
  }
}
</script>

<style lang="scss">
.front {
  height: 100vh;
  background: url('~assets/images/header-bg.jpg');
  display: table;
  width: 100%;
  background-position: center;
  background-size: cover;
  color: #fff;
  text-align: center;

  &__titles {
    vertical-align: middle;
    display: table-cell;
    &__sub {
      font-size: 40px;
      font-style: italic;
      line-height: 40px;
      margin-bottom: 25px;
      font-family: 'Droid Serif', -apple-system, BlinkMacSystemFont, 'Segoe UI',
        Roboto, 'Helvetica Neue', Arial, sans-serif, 'Apple Color Emoji',
        'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
    }

    &__main {
      font-size: 75px;
      font-weight: 700;
      line-height: 75px;
      margin-bottom: 50px;
      font-family: Montserrat, -apple-system, BlinkMacSystemFont, 'Segoe UI',
        Roboto, 'Helvetica Neue', Arial, sans-serif, 'Apple Color Emoji',
        'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
    }
  }
}
</style>
