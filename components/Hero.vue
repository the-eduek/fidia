<template>
  <section class="hero">
    <div class="hero__header">
      <h2>Welcome back, Olivia</h2>
      <p>Track, manage and forecast your customers and orders.</p>
    </div>

    <div class="hero__buttons">
      <button class="btn">
        <svg width="20" height="18" viewBox="0 0 20 18" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M13.3334 12.3334L10 9.00003M10 9.00003L6.6667 12.3334M10 9.00003V16.5M16.9917 14.325C17.8045 13.8819 18.4466 13.1808 18.8166 12.3322C19.1866 11.4837 19.2635 10.5361 19.0352 9.63893C18.8069 8.74182 18.2863 7.94629 17.5556 7.3779C16.8249 6.80951 15.9258 6.50064 15 6.50003H13.95C13.6978 5.52439 13.2277 4.61864 12.575 3.85085C11.9223 3.08307 11.1041 2.47324 10.1818 2.0672C9.25949 1.66116 8.25715 1.46949 7.25013 1.5066C6.2431 1.5437 5.25758 1.80861 4.36768 2.28142C3.47777 2.75422 2.70662 3.42261 2.11221 4.23635C1.51781 5.05008 1.1156 5.98797 0.935844 6.97952C0.756086 7.97107 0.803449 8.99047 1.07437 9.96108C1.3453 10.9317 1.83273 11.8282 2.50003 12.5834" stroke="#344054" stroke-width="1.67" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        <span>Import</span>
      </button>
      <button class="btn btn--main">
        <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M7.00002 1.16669V12.8334M1.16669 7.00002H12.8334" stroke="white" stroke-width="1.67" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        <span>Add</span>
      </button>
    </div>
  </section>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import '@/assets/styles/base/variables';

.hero {
  padding: 2rem 1rem;
  &__header {
    padding-bottom: 1.25rem;
    h2 {
      line-height: 32px;
    }
  }

  &__buttons {
    display: flex;
    .btn {
      margin-right: 12px;
      width: 105px;
      &--main {
        width: 88px;
        color: $white;
        background: $primary;
        border-color: $primary;
      }
    }
  }
}

@media (min-width: 1024px) {
  .hero {
    padding: 2rem 3rem 0;
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    &__header {
      padding-bottom: 0;
      h2 {
        font-size: 30px;
        line-height: 38px;
        padding-bottom: 4px;
      }
    }

    &__buttons {
      .btn {
        margin-left: 12px;
        margin-right: 0;
      }
    }
  }
}

@media (min-width: 1280px) {
  .hero {
    padding: 3rem 7rem 0;
  }
}
</style>