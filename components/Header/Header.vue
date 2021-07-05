<template>
  <header class="header">
    <div class="container header__container">
      <div class="left">
        <nuxt-link to="/" class="logo">CASINO</nuxt-link>
        <transition name="overflow-v">
          <div v-if="navIsOpened" class="overflow" :class="{'active':navIsOpened}" @click="navClose"></div>
        </transition>
        <nav class="nav" :class="{'nav-mobile_active':navIsOpened}">
          <ul class="list">
            <li class="item">
              <nuxt-link to="/" class="link" @click.native="navClose">Главная</nuxt-link>
            </li>
            <li class="item">
              <nuxt-link to="/how_to_play" class="link" @click.native="navClose">Как играть</nuxt-link>
            </li>
            <li class="item">
              <nuxt-link to="/FAQ" class="link" @click.native="navClose">FAQ</nuxt-link>
            </li>
            <li class="item">
              <nuxt-link to="/referrals" class="link" @click.native="navClose">Рефералы</nuxt-link>
            </li>
            <li class="item">
              <nuxt-link to="/bonus" class="link" @click.native="navClose">Бонусы</nuxt-link>
            </li>
          </ul>
          <div class="auth-container auth-container_mobile">
            <button class="btn login" @click="navClose">Вход</button>
            <button class="btn registration" @click="navClose">Регистрация</button>
          </div>
        </nav>
      </div>
      <div class="right">
        <div class="auth-container">
          <button class="btn login">Вход</button>
          <button class="btn registration">Регистрация</button>
        </div>
        <button class="burger" @click="navToggle">
          <svg xmlns="http://www.w3.org/2000/svg"
               width="30"
               height="30"
               viewBox="0 0 24 24"
               fill="none"
               stroke="currentColor"
               stroke-width="2"
               stroke-linecap="round"
               stroke-linejoin="round"
               :class="{'burger_active':navIsOpened}">
            <line x1="3" y1="12" x2="21" y2="12"></line>
            <line x1="3" y1="6" x2="21" y2="6"></line>
            <line x1="3" y1="18" x2="21" y2="18"></line>
          </svg>
        </button>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      navIsOpened: false,
    }
  },
  methods: {
    navToggle: function () {
      this.navIsOpened = !this.navIsOpened;
    },
    navClose: function () {
      this.navIsOpened = false;
    }
  }
}
</script>

<style scoped>
.header {
  z-index: 100;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  align-items: center;
  height: 60px;
  background-color: #fff;
  border-bottom: 1px solid rgba(72,94,144,.16);
}

.header__container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.left, .right {
  display: flex;
  align-items: center;
}

.logo {
  text-transform: uppercase;
  font-weight: 700;
  font-size: 26px;
  color: var(--notBlack);
  margin-right: 60px;
}

.burger {
  display: none;
  padding: 5px;
  justify-content: center;
  flex-direction: column;
}

.burger > svg > line {
  stroke: var(--notBlack);
}

.list {
  display: flex;
  white-space:nowrap;
  margin-right: 15px;
}


.item:not(:last-child)  {
  margin-right: 15px;
}

.auth-container {
  display: flex;
}

.auth-container_mobile {
  display: none;
  flex-direction: column;
}

.link {
  font-size: 14px;
  font-weight: 400;
  line-height: 1;
  transition: color .2s ease-in-out;
}

.link:hover{
  color: var(--blue);
}

.btn {
  padding: 7.5px 15px;
  text-transform: uppercase;
  font-size: 12px;
  font-weight: 600;
  letter-spacing: .5px;
  line-height: 1.75;
  border-radius: 4px;
  transition: color .15s ease-in-out,background-color .15s ease-in-out,border-color .15s ease-in-out;
}


.login {
  margin-right: 10px;
  background-color: #fff;
  border: 1px solid #c0ccda;
  color: rgba(27,46,75,.7);
}

.login:hover {
  border-color: #8392a5;
  color: #1b2e4b;
}

.registration {
  background-color: #015de1;
  color: #fff;
}
.registration:hover {
  background-color: #0153c7;
  border-color: #0153c7;
}

.overflow {
  opacity: 0;
}

@media all and (max-width: 768px) {
  .auth-container {
    margin-right: 15px;
  }

  .logo {
    margin-right: 15px;
  }

  .burger {
    display: flex;
  }

  .nav {
    position: fixed;
    top: 60px;
    display: flex;
    flex-direction: column;
    padding: 30px;
    background-color: var(--white);
    right: -50vw;
    width: 50vw;
    height: calc(100vh - 60px);
    font-size: 24px;
    transition: transform .4s ease-in-out;
  }

  .nav.nav-mobile_active {
    transform: translateX(-50vw);
  }

  .burger > svg line {
    transition: transform .4s ease-in-out, opacity .4s cubic-bezier(1,0, 1, 0);
    transform-origin: center;
  }

  .burger > .burger_active line:first-child {
    opacity: 0;
    transition: transform .4s ease-in-out, opacity .4s cubic-bezier(0,1, 0, 1);
  }

  .burger > .burger_active line:nth-child(2) {
    transform: rotate(45deg) translateY(6px);
  }

  .burger > .burger_active line:nth-child(3) {
    transform: rotate(-45deg) translateY(-6px);
  }


  .list {
    display: flex;
    flex-direction: column;
    margin-right: 0;
  }

  .item:not(:last-child) {
    margin-right: 0;
  }

  .item {
    padding: 10px 30px;
  }

  .link {
    font-size: 20px;
  }



  .overflow {
    position: fixed;
    top: 60px;
    left: 0;
    display: block;

    margin: 0 auto;
    width: 100vw;
    height: 100vh;
    transition: opacity .3s ease-in-out;
    opacity: .5;
    background-color: var(--black);
  }

  .overflow-v-enter-active, .overflow-v-leave-active {
    transition: opacity .5s;
  }
  .overflow-v-enter, .overflow-v-leave-to /* .fade-leave-active до версии 2.1.8 */ {
    opacity: 0;
  }

  .auth-container_mobile > .btn {
    margin-right: 0;
  }

  .auth-container_mobile  > .btn:not(:last-child) {
    margin-bottom: 10px;
  }
}

@media all and (max-width: 576px) {

  .nav {
    width: 100vw;
    right: -100vw;
  }

  .nav.nav-mobile_active {
    transform: translateX(-100vw);
  }

  .auth-container {
    display: none;
  }

  .auth-container_mobile {
    display: flex;
  }
}
</style>
