<template>
    <div class="cart">
        <h2>Cart</h2>
        <CartItem v-if="CART.length"/>
    </div>
</template>

<script>
import CartItem from './CartItem.vue'
import { mapGetters } from 'vuex'
export default {
    name: 'Cart',
    components: {
        CartItem
    },
    computed: {
        ...mapGetters([
            'CART'
        ])
    }
    
}
</script>


<style lang="scss">

</style>