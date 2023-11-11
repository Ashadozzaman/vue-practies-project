<template>
<div class="product-card">
    <div class="product-card_title">
        <div>
            {{ product.title }}
        </div>
        <div>
            <button v-if="product.like" @click="clickLike">Like</button>
            <button v-else @click="clickLike">UnLike</button>
        </div>
    </div>
    <div class="product-card_body">
        <img :src="product.thumbnail" alt="">
        <p>{{product.price}}</p>
    </div>
    <div class="product-card_footer">
        <button @click="handleByNowClick">Buy Now</button>
        <button @click="handleAddToCartClick">Add to Cart</button>
    </div>
</div>
</template>

<script>
export default {
    mounted() {
        console.log(this.$slots.footer);
    },
    emits: {
        "buy-add-to-cart-clicked": function (data) {
            if (!data) {
                console.error("Data missing");
                return false;
            }
            return true;

        }
    },
    props: {
        product: {
            type: Object,
            default: () => {}
        }
    },
    methods: {
        handleByNowClick() {
            this.$emit('buy-now-clicked');
        },
        handleAddToCartClick() {
            this.$emit('buy-add-to-cart-clicked', this.product);
        },
        clickLike() {
            this.$emit('toogle-clicked-like', this.product);
        }
    }
};
</script>

<style>
.product-card {
    width: 200px;
    border: 1px solid #006f88;
    min-height: 100px;
    margin: 22px auto;
}

.product-card_title {
    background: #167db1;
    padding: 5px 11px;
    color: #fff;
    display: flex;
}

.product-card_body {
    padding: 11px;
    text-align: center;
}

.product-card_body img {
    height: 111px;
}

.product-card_footer {
    background: #6c7273;
    text-align: center;
    padding: auto;
}
</style>
