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
            <p>Quantity</p>
            {{cartItemData.quantity}}
        </div>
        <button @click="deleteFromCart">Delete</button>
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
        },
        methods: {
            deleteFromCart(){
                this.$emit('deleteFromCart')  // просто сообщаем что была нажата кнопка delete  
            }
        },
        mounted(){
            this.$set(this.cartItemData, 'quantity', 1) // $set обязательно иначе потеряем реактивность
        }
    }
</script>
<style lang="scss">
    .cartItem{
        display: flex;
        justify-content: space-around;
        align-items: center;
        flex-wrap: nowrap;
        box-shadow: 0 0 8px 0 #e0e0e0;
        padding: 20px;
        margin-bottom: 30px;
        &__img {
            max-width: 50px;
        }
    }
</style>