<template>
  <div v-if="products.length === 0">
    <p class="sr-only">products are loading</p>
    <div class="commercetools-skeleton-total-products"></div>
    <div class="commercetools-skeleton-filter"></div>
    <div class="commercetools-skeleton-products">
      <div class="commercetools-skeleton-products__item">
        <div class="commercetools-skeleton-products__header"></div>
        <div class="commercetools-skeleton-products__image"></div>
      </div>
      <div class="commercetools-skeleton-products__item">
        <div class="commercetools-skeleton-products__header"></div>
        <div class="commercetools-skeleton-products__image"></div>
      </div>
      <div class="commercetools-skeleton-products__item">
        <div class="commercetools-skeleton-products__header"></div>
        <div class="commercetools-skeleton-products__image"></div>
      </div>
      <div class="commercetools-skeleton-products__item">
        <div class="commercetools-skeleton-products__header"></div>
        <div class="commercetools-skeleton-products__image"></div>
      </div>
      <div class="commercetools-skeleton-products__item">
        <div class="commercetools-skeleton-products__header"></div>
        <div class="commercetools-skeleton-products__image"></div>
      </div>
      <div class="commercetools-skeleton-products__item">
        <div class="commercetools-skeleton-products__header"></div>
        <div class="commercetools-skeleton-products__image"></div>
      </div>
      <div class="commercetools-skeleton-products__item">
        <div class="commercetools-skeleton-products__header"></div>
        <div class="commercetools-skeleton-products__image"></div>
      </div>
      <div class="commercetools-skeleton-products__item">
        <div class="commercetools-skeleton-products__header"></div>
        <div class="commercetools-skeleton-products__image"></div>
      </div>
      <div class="commercetools-skeleton-products__item">
        <div class="commercetools-skeleton-products__header"></div>
        <div class="commercetools-skeleton-products__image"></div>
      </div>
      <div class="commercetools-skeleton-products__item">
        <div class="commercetools-skeleton-products__header"></div>
        <div class="commercetools-skeleton-products__image"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductsSkeleton',
  props: {
    products: Array,
  },
};
</script>
