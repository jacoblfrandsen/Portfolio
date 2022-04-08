
<template>
<div>
    <h1 class="empty">Shopping Cart</h1>
    <div class="empty" v-if="this.$root.$data.cart.length === 0">
      Your cart is Empty!
    </div>
    <div v-else>
      <CartList :items="items" />
    </div>
</div>
</template>


<script>
import CartList from "../components/CartList.vue"
export default {
  name: 'Cart-C',
  components: {
    CartList
  },
  data() {
    return {
      searchText: '',
    }
  },
  computed: {
    items() {
      return this.$root.$data.cart;
    }
  },
  methods: {
    select(){
      return '';
    }
  }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}

form {
  display: table;
  width: 100%;
}

i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}

.empty{
    text-align:center;
}
</style>
