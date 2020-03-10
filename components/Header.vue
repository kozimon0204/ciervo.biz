<template>
  <header
    id="top"
    class="header"
  >
    <div class="container">
      <div class="header__row">
        <button
          class="header-menu-trg"
          @click="toggle"
        ><i class="material-icons">menu</i></button>
        <p class="header__logo"><nuxt-link to="/">Ciervo</nuxt-link></p>
        <nav
          :class="{ opened: isOpen }"
          class="header-menu"
        >
          <nuxt-link to="/">Top</nuxt-link>
          <!-- 
          <nuxt-link to="/about">About</nuxt-link>
          <span class="disabled">Recruit</span>
          <span class="disabled">Contact</span>
          -->
        </nav>
        <div
          :class="{ opened: isOpen }"
          class="header-menu-back"
          @click="toggle"
        />
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data: function() {
    return {
      isOpen: false
    }
  },

  methods: {
    toggle: function(event) {
      this.isOpen = !this.isOpen
    }
  },
  head: {
    link: [
      {
        rel: 'stylesheet',
        href: 'https://fonts.googleapis.com/css?family=Kaushan+Script'
      }
    ]
  }
}
</script>


<style lang="scss">
.header {
  line-height: 64px;
  z-index: 10;
  position: fixed;
  width: 100%;
  color: #fff;

  &__logo {
    font-weight: bold;
    font-size: 1.75em;
    color: #fed136;
    font-family: 'Kaushan Script', -apple-system, BlinkMacSystemFont, 'Segoe UI',
      Roboto, 'Helvetica Neue', Arial, sans-serif, 'Apple Color Emoji',
      'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  }
  &__row {
    display: flex;
    justify-content: space-between;
    @media screen and (max-width: 700px) {
      justify-content: flex-start;
      margin: 0 -16px;
    }
  }
}

.header-menu-trg {
  width: 64px;
  display: none;
  @media screen and (max-width: 700px) {
    display: block;
  }
}

.header-menu-back {
  background: #fff;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  transition: 0.3s;
  opacity: 0;
  pointer-events: none;
  &.opened {
    opacity: 0.3;
    pointer-events: all;
  }
}

.header-menu {
  display: flex;
  @media screen and (max-width: 700px) {
    display: block;
    position: fixed;
    top: 0;
    left: 0;
    width: 200px;
    height: 100%;
    background: #fff;
    box-shadow: 0 0 16px rgba(#333, 0.3);
    z-index: 10;
    transform: translateX(-120%);
    transition: 0.3s;
    &.opened {
      transform: translateX(0);
    }
  }
  a,
  span {
    line-height: 64px;
    font-weight: bold;
    padding: 0 24px;
    display: block;
    position: relative;
    font-size: 13px;
    letter-spacing: 1px;
    text-transform: uppercase;
    &.nuxt-link-exact-active {
      &:after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 0;
        display: block;
        width: 100%;
        height: 4px;
        background: #fff;
        @media screen and (max-width: 700px) {
          width: 4px;
          height: 100%;
        }
      }
    }
  }
  .disabled {
    opacity: 0.3;
  }
}
</style>
