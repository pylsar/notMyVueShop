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
        deleteFromCart(index){
            console.log(index)
        }
    }
    
    
}
</script>


<style lang="scss">

</style>