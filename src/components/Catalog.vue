<template>
    <div class="catalog">
        <h1>Catalog 5-2030</h1>
        <div class="catalog__list">
        <CatalogItem 
            v-for='product in PRODUCTS'
            :key="product.article"
            :productData='product'
            @addToCart='addToCart'
        />
        </div>
    </div>
</template>

<script>
import CatalogItem from '@/components/CatalogItem'
import {mapActions, mapGetters} from 'vuex'

export default {
    name: 'Catalog',
    components: {
        CatalogItem,
    },
    data(){
        return {

        }
    },
    computed:{
        ...mapGetters([
            'PRODUCTS'
        ])
    },
    methods:{
        ...mapActions([
            'GET_PRODUCTS_FROM_API',
            'ADD_TO_CART'
        ]),
        addToCart(data){
            this.ADD_TO_CART(data)
        }
    },
    mounted(){
        this.GET_PRODUCTS_FROM_API()
    }
    
}
</script>


<style lang="scss">
    .catalog {
        &__list {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            align-items: center;
        }
    }
</style>