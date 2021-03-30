<template>
  <b-card :title="name" :sub-title="symbol" class="mb-3 stock-card">
    <b-card-text class="--current-value">
      {{ current }}
      <template v-if="priceChange > 0">
        <span class="value-status--positive ml-2">
          <b-icon-arrow-up></b-icon-arrow-up>
          {{ priceChange }}
          <span class="value-percent--positive">({{ percentChange }}%)</span>
        </span>
      </template>
      <template v-else>
        <span class="value-status--negative ml-2">
          <b-icon-arrow-down></b-icon-arrow-down>
          {{ priceChange }}
          <span class="value-percent--negative">({{ percentChange }}%)</span>
        </span>
      </template>
    </b-card-text>
    <b-card-text class="--stats">
      OPEN <span class="stat-value">{{ open }}</span> HIGH
      <span class="stat-value">{{ high }}</span> LOW
      <span class="stat-value">{{ low }}</span>
    </b-card-text>
  </b-card>
</template>

<script>
export default {
  name: "StockCard",
  props: {
    name: String,
    symbol: String,
    current: String,
    open: String,
    high: String,
    low: String,
  },
  priceChange: 0,
  percentChange: 0,

  created() {
    this.valueChange();
    this.percentChange();
  },
  methods: {
    valueChange() {
      if (this.current > this.open) {
        this.priceChange = (Math.round((this.current - this.open) * 100) / 100).toFixed(2);
      } else if (this.current < this.open) {
        this.priceChange = -Math.abs(
          (Math.round((this.open - this.current) * 100) / 100).toFixed(2));
      }
      return this.priceChange;
    },

    percentChange() {
      return this.percentChange = ((this.priceChange / this.open) * 100).toFixed(2);
    },
  },
};
</script>
