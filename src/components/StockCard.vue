<template>
  <b-card title="ALPHABET INC. CL C" sub-title="GOOG" class="mb-3 stock-card">
    <b-card-text class="--current-value">
      706.32
      <span class="value-status ml-2">
        <b-icon-arrow-up></b-icon-arrow-up>
        15.32
        <span class="value-percent">(2.22%)</span>
      </span>
    </b-card-text>
    <b-card-text class="--stats">
      OPEN <span class="stat-value">691</span> HIGH
      <span class="stat-value">709.28</span> LOW
      <span class="stat-value">689.47</span>
    </b-card-text>
  </b-card>
</template>

<script>
export default {
  name: 'StockCard',
  props: {
    name: String,
    company: String,
    current_value: String,
    open_value: String,
    high_value: String,
    low_value: String
  },
  created() {
    this.valuePercentChange();
  },
  methods: {
    valuePercentChange() {
      
    }
  }
}
</script>

<style lang="scss">
.stock-card {
  box-shadow: 0px 5px 25px 7px rgba(145, 154, 160, 0.4);
  width: 25rem;

  .card-title {
    color: var(--type);
    font-size: 1rem;
    font-weight: 800;
  }

  .card-subtitle {
    color: var(--caption);
    font-size: 0.8rem;
    font-weight: 600;
  }

  .value-status {
    color: var(--green-dark);
    font-size: 0.8rem;
    font-weight: 600;
  }

  .value-percent {
    color: var(--green-light);
  }

  .card-text.--current-value {
    color: var(--type);
    font-size: 1.5rem;
  }

  .card-text {
    &.--stats {
      color: var(--caption);
      font-size: 0.8rem;
      font-weight: 600;

      .stat-value {
        color: var(--type);
        margin: 5px;
      }
    }
  }
}
</style>