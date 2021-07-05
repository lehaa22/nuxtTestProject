<template>
  <div>
    <jopa_nevidimka/>
    <Header />
    <div class="container main-container">
      <div class="row">
        <div class="col-12 col-lg-2">
          <h2 class="change-game">Выбор игры</h2>
          <ul class="second-nav">
            <li class="second-nav__item">
              <nuxt-link to="/games/dice">
                <div class="second-nav__avatar">
                  <DiceSvg />
                </div>
                <div class="second-nav__name">
                  Dice
                </div>
              </nuxt-link>
            </li>
            <li class="second-nav__item">
              <nuxt-link to="/games/dice">
                <div class="second-nav__avatar">
                  <MinesSvg />
                </div>
                <div class="second-nav__name">
                  Mines
                </div>
              </nuxt-link>
            </li>
          </ul>
        </div>
        <Nuxt />
      </div>
    </div>
  </div>
</template>

<script>
import Header from '@/components/Header/Header';
import Footer from '@/components/Footer';
import jopa_nevidimka from '@/components/Header/jopa_nevidimka';
import DiceSvg from '@/assets/icons/Dice'
import MinesSvg from '@/assets/icons/Mines'
export default {
  components: {
    Header,
    Footer,
    jopa_nevidimka,
    DiceSvg,
    MinesSvg,
  },
}
</script>

<style scoped>
.main-container {
  z-index: 1;
  margin-top: 60px;
  height: 1000px;
  padding-top: 15px;
}

.second-nav {
  margin-bottom: 15px;
}

.change-game {
  color: var(--notBlack);
  font-weight: 600;
  text-transform: uppercase;
  font-size: 28px;
}

.second-nav__item {
  cursor: pointer;
}

.second-nav__item a {
  display: flex;
  align-items: center;
}

.second-nav__item:not(:last-child) {
  margin-bottom: 15px;
}

.second-nav__avatar {
  margin-right: 15px;
  font-size: 0;
  padding: 9px;
  border-radius: 25%;
  display: inline-block;
  color: var(--white);
  background-image: linear-gradient(45deg, rgb(74, 89, 130) 0%, rgb(4, 25, 97) 100%);
}

.second-nav__item:hover a {
  color: var(--blue)
}
.second-nav__item:hover .second-nav__avatar {
  background-image: linear-gradient(45deg, #1c65c9 0%, #2c80ff 100%);
}

.second-nav__name {
  font-size: 18px;
}


</style>
