<template>
    <div class="cart">
        <h2>Cart</h2>
        <CartItem 
            v-for="item in cartData"
            :key='item.article'
            :cartItemData='item'
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
    }
    
    
}
</script>


<style lang="scss">

</style>