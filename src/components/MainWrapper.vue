<template>
    <div class="main-wrapper">
        <Catalog />
        <Cart 
            v-if="CART.length"
            :cartData='CART'
        />
    </div>
</template>   

<script>
import Catalog from '@/components/Catalog';
import Cart from '@/components/Cart';
import { mapGetters } from 'vuex'


export default {
    name: 'MainWrapper',
    components: {
        Catalog,
        Cart
    },
    computed: {
        ...mapGetters([
            'CART'
        ])
    }
}
</script>

<style lang="scss">
    .main-wrapper{
        max-width: 900px;
        margin: 0 auto;
    }
</style>