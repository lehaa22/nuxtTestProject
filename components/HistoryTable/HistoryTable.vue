<template>
  <div class="history-table">
    <div class="desc">
      <div class="name">
        История
      </div>
      <div class="history-mode">
        <button
          class="btn history-mode__btn history-mode__btn_left"
          :class="{'history-mode__btn_active':isHistoryModeAll}"
          @click="changeHistoryMode(true)"
        >
          Все игры
        </button>
        <button
          class="btn history-mode__btn history-mode__btn_right"
          :class="{'history-mode__btn_active':!isHistoryModeAll}"
          @click="changeHistoryMode(false)"
        >
          Мои игры
        </button>
      </div>
    </div>
    <div class="table-container">
      <table class="table">
        <thead>
        <tr class="table__tr">
          <th class="table__th">Игра</th>
          <th class="table__th">Логин</th>
          <th class="table__th">Сумма</th>
          <th class="table__th">Коэф</th>
          <th class="table__th">Результат</th>
        </tr>
        </thead>
        <tbody>
        <tr class="table__tr" v-for="data in tableHistoryData" :key="data.game">
          <td class="table__td">{{ data.game }}</td>
          <td class="table__td">{{ data.login }}</td>
          <td class="table__td">{{ data.sum}}</td>
          <td class="table__td">{{ data.ratio }}</td>
          <td class="table__td">{{ data.result }}</td>
        </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {

  data() {
    return {
      isHistoryModeAll: true,
      tableHistoryData: [
        {game:121,login:'lehaa22',sum:1000,ratio:49.95,result:2000},
        {game:122,login:'lehaa22',sum:1000,ratio:49.95,result:2000},
        {game:123,login:'lehaa22',sum:1000,ratio:49.95,result:2000},
        {game:124,login:'lehaa22',sum:1000,ratio:49.95,result:2000},
        {game:125,login:'lehaa22',sum:1000,ratio:49.95,result:2000},
      ]
    };
  },
  methods: {
    changeHistoryMode(mode) {
      this.isHistoryModeAll = mode;
    }
  }
}
</script>

<style scoped>
.history-table {
  background-color: var(--white);
  border-radius: 4px;
  box-shadow: 0 0 10px rgba(28,39,60,.05);
  border: 1px solid rgba(72,94,144,.16);
}

.desc {
  display: flex;
  justify-content: space-between;
  padding: 15px;
  align-items: center;
}
.history-mode {
  font-size: 0;
}

.history-mode__btn {
  font-size: 14px;
  padding: 5px 15px;
  color: rgba(27,46,75,.7);
  border: 1px solid #8392a5;
  border-radius: 4px;
}

.history-mode__btn:focus {
  outline: none;
}

.history-mode__btn:hover {
  border-color: rgba(27,46,75,.7);
  color: #1b2e4b;
}

.history-mode__btn_left {
  border-radius:4px 0 0 4px;
}

.history-mode__btn_right {
  border-left: none;
  border-radius:0 4px 4px 0;
}

.history-mode__btn_active {
  background-color: #f5f6fa;
}

.table {
  width: 100%;
  border-collapse: collapse;
}

.table__th, .table__td {
  white-space: nowrap;
  padding: 10px 0;
  font-size: 14px;
}

.table__tr {
  border-top: 1px solid #e5e9f2;
}

.table__th {

  font-weight: 500;
  letter-spacing: 1px;
  text-transform: uppercase;
  color: #8392a5;
}

.table__td {
  text-align: center;
}

@media all and (max-width: 425px) {
  .table {
    min-width: 425px;

  }
  .table-container {
    width: 100%;
    overflow-x: scroll;
  }
}
</style>
