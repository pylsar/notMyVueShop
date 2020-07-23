<template>
    <div class="catalogItem">
        <span>{{productData.name}}</span>
        <img class="catalogItem__image" :src=" require('../assets/images/' + productData.image) " alt="">
        <p>price: {{productData.price}} P.</p>
        <button @click="sendDataToParent">add to cart</button>
    </div>
</template>

<script>
export default {
    name: 'CatalogItem',
    props: {
        productData: {  // productData надо связать с product в родителе
            type: Object,
            default(){
                return{}  // дефолтное состояние до получения объектов
            }
        }
    },
    methods:{
        sendDataToParent(){
            this.$emit('sendArticle', this.productData.article) //придумываем название для родителя и что надо передать
        }
    }
    
}
</script>


<style lang="scss">
    .catalogItem {
        flex-basis: 25%;
        box-shadow: 0 0 8px 0 #e0e0e0;
        padding: 20px;
        margin-bottom: 30px;
        &__image{
            width: 150px;
        }
    }
</style>