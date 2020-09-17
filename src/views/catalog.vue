<template>
  <main class="main">
    <div class="catalog">
      <h2>Ты сегодня покормил кота?</h2>
      <div class="catalog-list">
        <catalogItem v-for="item in catalogList" :key="item" :catalogItem="item" />
      </div>
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
    }
  }
</script>

<style>
  @import '../assets/styles/catalog.css';
</style>