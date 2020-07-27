<template>
    <div class="cartItem">
        <img 
            class="cartItem__img"
            :src=" require('../assets/images/' + cartItemData.image)" 
            alt=""
        >
        <div class="cartItem__info">
            <p>{{cartItemData.name}}</p>
            <p>{{cartItemData.price}}</p>
            <p>{{cartItemData.article}}</p>
        </div>
        <div class="cartItem__quantity">

        </div>
        <button>Delete</button>
    </div>
</template>    

<script>
    export default {
        name: 'CartItem',
        props: {
            cartItemData: {
                type: Object,
                default(){
                    return {}
                }
            }
        }
    }
</script>
<style lang="scss">
    .cartItem{
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: nowrap;
        &__img {
            max-width: 50px;
        }
    }
</style>