<template>
  <catalogItem :catalogItem="catalogList" />
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