<template>
    <div class="cart">
        <h2>Cart</h2>
        <CartItem 
            v-for="(item, index) in cartData"
            :key='item.article'
            :cartItemData='item'
            :deleteFromCart='deleteFromCart(index)'
        />
    </div>
</template>

<script>
import CartItem from './CartItem.vue'
import {mapActions} from 'vuex'

export default {
    name: 'Cart',
    components: {
        CartItem
    },
    props: {
        cartData: {
            type: Array,
            default(){
                return[]
            }
        }
    },
    methods:{
        ...mapActions([
            'DELETE_FROM_CART'
        ]),
        deleteFromCart(index){
            this.DELETE_FROM_CART(index)
        }
    }
    
    
}
</script>


<style lang="scss">

</style>