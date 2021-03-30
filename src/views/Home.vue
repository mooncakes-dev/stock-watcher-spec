<template>
  <div class="container">
    <div class="header">
      <h2 class="title">Stock Watcher</h2>
      <b-form inline>
        <b-form-input
          size="lg"
          class="mb-2 mr-sm-2 mb-sm-0 stock-input"
          placeholder="Enter stock symbol"
        >
        </b-form-input>
        <b-button class="stock-btn" size="lg" variant="button">
          ADD STOCK
        </b-button>
      </b-form>
    </div>
    <div class="main">
      <StockCard
        v-for="stock in stocks"
        :key="stock.symbol"
        :name="stock.name"
        :symbol="stock.symbol"
        :open="stock.open"
        :high="stock.high"
        :low="stock.low"
        :current="stock.current"
      ></StockCard>
    </div>
  </div>
</template>

<script>
import StockCard from "@/components/StockCard.vue";

export default {
  name: "Home",
  components: {
    StockCard,
  },
  data() {
    return {
      stocks: [
        {
          name: "Alphabet Inc. CL C",
          symbol: "GOOG",
          current: "706.32",
          open: "691",
          high: "709.28",
          low: "689.47",
        },
        {
          name: "YAHOO! Inc",
          symbol: "YHOO",
          current: "29.27",
          open: "29.28",
          high: "29.66",
          low: "29.06",
        },
        {
          name: "American International",
          symbol: "AIG",
          current: "53.08",
          open: "52.06",
          high: "53.47",
          low: "52.28",
        },
        {
          name: "Groupon Inc",
          symbol: "GRPN",
          current: "3.74",
          open: "4.08",
          high: "4.13",
          low: "3.60",
        },
        {
          name: "3x Inverse Crude",
          symbol: "DWTIF",
          current: "253.41",
          open: "307.10",
          high: "297.50",
          low: "245.59",
        },
      ],
    };
  },
};
</script>
