<template>
  <div :class="['catalog-item', { 'catalog-item--disabled' : catalogItem.active }]">
    <div class="catalog-item__block">
      <div class="catalog-item__top">
        <p class="catalog-item__text">Сказачное заморское яство</p>
        <p class="catalog-item__title">
          Нямушка <br>
          <span class="catalog-item__title--small">с {{ catalogItem.fill }}</span>
        </p>
        <p class="catalog-item__info" v-if="catalogItem.countPortion"><span class='text--bold' v-html="catalogItem.countPortion"></span> порций</p>
        <p class="catalog-item__info" v-if="catalogItem.gift"><span v-html="catalogItem.gift"></span> в подарок</p>
        <p class="catalog-item__info" v-if="catalogItem.add">{{ catalogItem.add }}</p>
      </div>
      <div class="catalog-item__bottom">
        <div class="catalog-item__param"><span class="catalog-item__param-count">{{ catalogItem.countKg }}</span><br> кг</div>
      </div>
    </div>
    <div class="catalog-item__other" v-html="catalogItem.text"></div>
  </div>
</template>

<script>
export default {
  name: 'catalogItem',
  props: ['catalogItem']
}
</script>

<style>
  @import '../assets/styles/catalogItem.css';
</style>