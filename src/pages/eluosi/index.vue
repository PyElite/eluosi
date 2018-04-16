<template>
<div class="wrap">
  <div class="game">
    <div class="game-row"
    v-for='(row, rowIndex) in layout'>
      <div class="game-cell"
      v-for='(cell, cellIndex) in row'>

      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      layout: [],
    };
  },

  methods: {
    initLayout(rows, cells) {
      const arr = [];
      for (let r = 0; r < rows; r++) {
        const ass = [];
        for (let c = 0; c < cells; c++) {
          ass.push(c);
        }
        arr.push(ass);
      }
      this.layout = arr;
    },
  },

  created() {
    this.initLayout(15, 10);
  },
};
</script>

<style scoped>
.wrap {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
}
.game-cell {
  width: 50rpx;
  height: 50rpx;
  border: 1px solid #fff;
  background-color: #192122;
}
.game-row {
  display: flex;
}
.game {
  margin: 0 auto;
}
</style>
