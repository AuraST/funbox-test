<template>
  <main class="main">
    <div class="catalog">
      <h1>Ты сегодня покормил кота?</h1>
      <ul class="catalog-list">
        <catalogItem v-for="item in catalogList" :key="item" :catalogItem="item" :onClick="chooseItem" />
      </ul>
    </div>
  </main>
</template>

<script>
  import catalogItem from '@/components/catalogItem'

  export default {
    name: "catalog",
    data () {
        return {
            catalogList: {}
        }
    },
    mounted() {
        fetch('../data/catalog.json')
        .then(response => response.json())
        .then(json => {
            this.catalogList = json
        })
    },
    components: {
        catalogItem
    },
    methods: {
      chooseItem(selectedItem) {
        this.catalogList = this.catalogList.map(item => {
          if (selectedItem.id === item.id && !item.disabled) {
            item.selected = !item.selected
          }
          return item
        })
      }
    }
  }
</script>

<style>
  @import '../assets/styles/catalog.css';
</style>