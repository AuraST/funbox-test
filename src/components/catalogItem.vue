<template>
  <li :class="['catalog-item', { 'catalog-item--disabled' : catalogItem.active }]">
    <div :class="[ 'catalog-item__card', { 'catalog-item__card--choose' : catalogItem.selected === true }]" @click="onClickItem">
      <div class="catalog-item__block">
        <div class="catalog-item__top">
          <p class="catalog-item__text">Сказачное заморское яство</p>
          <p class="catalog-item__title">
            Нямушка <br>
            <span class="catalog-item__title--small">с {{ catalogItem.fill }}</span>
          </p>
          <p class="catalog-item__info" v-if="catalogItem.countPortion"><span class='text--bold'>{{ catalogItem.countPortion }}</span> порций</p>
          <p class="catalog-item__info" v-if="catalogItem.gift"><span v-html="catalogItem.gift"></span> в подарок</p>
          <p class="catalog-item__info" v-if="catalogItem.add">{{ catalogItem.add }}</p>
        </div>
        <div class="catalog-item__bottom">
          <div class="catalog-item__param">
            <p class="catalog-item__param-count">
              <span class="catalog-item__param-value">{{ catalogItem.countKg }}</span><br> 
              кг
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="catalog-item__other">
      <p class="catalog-item__other-text" v-html="catalogItem.text"></p>
    </div>
  </li>
</template>

<script>
export default {
  name: 'catalogItem',
  props: ['catalogItem', 'onClick'],
  methods: {
    onClickItem() {
      this.onClick(this.catalogItem)
    }
  }
}
</script>

<style>
  @import '../assets/styles/catalogItem.css';
</style>