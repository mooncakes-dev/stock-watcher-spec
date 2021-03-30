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
      <StockCard></StockCard>
    </div>
  </div>
</template>

<script>
import StockCard from '@/components/StockCard.vue'

export default {
  name: 'Home',
  components: {
    StockCard
  }
}
</script>

<style lang="scss">
$gap: 4vh;
.container {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  gap: $gap;
  justify-content: flex-start;
  min-height: 100vh;

  .header {
    display: flex;
    flex-direction: column;
    flex-basis: 100%;
    height: 20vh;
    gap: $gap;

    .title {
      color: var(--type);
      font-size: 50px;
      font-weight: 700;
      margin-top: 4vh;
    }

    .stock-input {
      background-color: #f5f5f5;
      font-size: 0.9rem;
      padding: 1.4rem 2.5rem 1.4rem 1rem;
    }

    .stock-btn {
      box-shadow: 0px 5px 25px 7px rgba(145, 154, 160, 0.4);
      font-weight: 700;
      font-size: 0.8rem;
      padding: 0.8rem 2rem;
    }
  }

  .main {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: $gap;
  }
}
</style>