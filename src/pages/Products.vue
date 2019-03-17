<template>
  <q-page padding>
    <q-table :title="$t('mainMenu.products')" :data="products" :columns="productFields" row-key="id" />
  </q-page>
</template>

<script>
  export default {
    name: 'Products',
    data() {
      return {
        products: [{
          id: 1,
          name: "Strawberries - California",
          price: "$21.53",
          quantity: 14
        }, {
          id: 2,
          name: "Appetizer - Southwestern",
          price: "$74.01",
          quantity: 10
        }, {
          id: 3,
          name: "Potatoes - Yukon Gold, 80 Ct",
          price: "$29.86",
          quantity: 10
        }, {
          id: 4,
          name: "Peach - Fresh",
          price: "$70.12",
          quantity: 12
        }, {
          id: 5,
          name: "Sauce - Balsamic Viniagrette",
          price: "$50.00",
          quantity: 18
        }, {
          id: 6,
          name: "Mace Ground",
          price: "$51.42",
          quantity: 18
        }, {
          id: 7,
          name: "Dill Weed - Dry",
          price: "$98.08",
          quantity: 18
        }, {
          id: 8,
          name: "Towel Multifold",
          price: "$80.31",
          quantity: 12
        }, {
          id: 9,
          name: "Rice - Brown",
          price: "$82.54",
          quantity: 18
        }, {
          id: 10,
          name: "Brandy Cherry - Mcguinness",
          price: "$25.45",
          quantity: 13
        }, {
          id: 11,
          name: "Muffin Mix - Raisin Bran",
          price: "$52.20",
          quantity: 15
        }, {
          id: 12,
          name: "Island Oasis - Peach Daiquiri",
          price: "$59.76",
          quantity: 3
        }, {
          id: 13,
          name: "Liqueur - Melon",
          price: "$38.06",
          quantity: 16
        }, {
          id: 14,
          name: "Table Cloth 53x69 White",
          price: "$60.94",
          quantity: 1
        }, {
          id: 15,
          name: "Bagel - Everything Presliced",
          price: "$47.08",
          quantity: 12
        }, {
          id: 16,
          name: "Bread - Multigrain",
          price: "$27.48",
          quantity: 3
        }, {
          id: 17,
          name: "Venison - Striploin",
          price: "$57.73",
          quantity: 19
        }, {
          id: 18,
          name: "Yucca",
          price: "$32.34",
          quantity: 11
        }, {
          id: 19,
          name: "Sauce - Cranberry",
          price: "$44.12",
          quantity: 10
        }, {
          id: 20,
          name: "Versatainer Nc - 9388",
          price: "$40.42",
          quantity: 19
        }]
      }
    },
    computed: {
      productFields() {
        return [{
            name: 'Name',
            required: true,
            label: this.$t('product.name'),
            align: 'left',
            field: 'name',
            sortable: true
          },
          {
            name: 'Price',
            align: 'center',
            label: this.$t('product.price'),
            field: 'price',
            sortable: true
          },
          {
            name: 'Quantity',
            label: this.$t('product.quantity'),
            field: 'quantity',
            sortable: true
          }
        ]
      }
    }
  }
</script>

<style>

</style>
