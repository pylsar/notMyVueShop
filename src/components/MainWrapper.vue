<template>
    <div class="main-wrapper">
        <Catalog />
        <Cart />
    </div>
</template>   

<script>
import Catalog from '@/components/Catalog';
import Cart from '@/components/Cart';


export default {
    name: 'MainWrapper',
    components: {
        Catalog,
        Cart
    }
}
</script>

<style lang="scss">
    .main-wrapper{
        max-width: 900px;
        margin: 0 auto;
    }
</style>