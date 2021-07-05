<template>
  <li class="col-6 col-lg-3">
    <div class="card">
      <nuxt-img class="game-list__avatar" :src="img" alt="" />
      <div class="card-info">
        <div class="game-list__name">
          {{name}}
        </div>
        <nuxt-link :to="linkPath" class="game-list__button">
          Играть
        </nuxt-link>
      </div>
    </div>
  </li>
</template>

<script>
export default {
  props:{
    'name': String,
    'linkPath': String,
    'img': String,
  },

}
</script>

<style scoped>
.card {
  font-size: 0;
  border-radius: 4px;
  background-color: var(--white);
  box-shadow: 0 0 10px rgba(28,39,60,.05);
  border: 1px solid rgba(72,94,144,.16);
  margin-bottom: 15px;
}

.game-list__avatar {
  border-radius: 4px 4px 0 0;
}

.card-info {
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  align-items: center;
  padding:  20px;
}

.game-list__name {
  font-size: 21px;
  margin-bottom: 15px;
}

.game-list__button {
  width: 100%;
  padding: 8px 15px;
  border: #c0ccda solid 1px;
  border-radius: 4px;
  text-align: center;
  font-size: 15px;
  color: rgba(27,46,75,.7);
  transition: color .15s ease-in-out,background-color .15s ease-in-out,border-color .15s ease-in-out,box-shadow .15s ease-in-out;
}

.game-list__button:hover {
  color: #001737;
  border-color: #8392a5;
}

</style>
