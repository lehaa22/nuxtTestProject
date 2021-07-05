<template>
  <div class="col-12 col-lg-10">
    <ul class="game-list row">
      <CardList name="Dice" linkPath="/games/dice" img="/images/avatar_dice.jpg"/>
      <CardList name="Mines" linkPath="/games/mines" img="/images/avatar_mines.jpg"/>
      <CardList name="Coin" linkPath="/games/coin" img="/images/avatar_coin.jpg"/>
      <CardList name="Wheel" linkPath="/games/wheel" img="/images/avatar_wheel.jpg"/>
    </ul>
    <HistoryTable />
  </div>
</template>

<script>
import CardList from '@/components/pages/index/CardList';
import HistoryTable from "@/components/HistoryTable/HistoryTable";
export default {
  components: {
    CardList,
    HistoryTable,
  }
}
</script>

<style scoped>


</style>
