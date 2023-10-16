<template>
    <div class="credit-card">
        <label>Name On Card</label>
        <input type="text" :value="nameOnCard" @input="handleInput('update:nameOnCard', $event)">
        <label>Card Number</label>
        <input type="text" :value="cardNumber" @input="handleInput('update:cardNumber', $event)">
        <div class="row">
            <div class="col-md-6">
                <label>Expire</label>
                <input type="date" :value="expire" @input="handleInput('update:expire', $event)">
            </div>
            <div class="col-md-6">
                <label>CVV</label>
                <input type="text" :value="cvv" @input="handleInput('update:cvv', $event)">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        nameOnCard: {
            type: Number,
            default: ""
        },
        cardNumber: {
            type: String,
            default: ""
        },
        expire: {
            type: String,
            default: ""
        },
        cvv: {
            type: String,
            default: ""
        },
    },
    methods: {
        handleInput(name, e) {
            this.$emit(name, e.target.value);
        }
    },
}
</script>

<style>
.credit-card {
    width: 300px;
    border: 1px solid gray;
    padding: 22px;
    border-radius: 5px;
    background-color: rgb(255, 254, 247);
    color: rgb(82, 82, 82);
    min-height: 111px;
}

input {
    padding: 7px 9px;
    margin-bottom: 11px;
    border-radius: 3px;
    width: 100%;
    border: 1px solid gray;
}

.row {
    display: flex;
}
.col-md-6{
    width: 85%;
}
</style>