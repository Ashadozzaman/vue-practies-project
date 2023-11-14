<template>
    <div class="credit-card">
        <label>Write your comment bellow</label>
        <textarea cols="3" rows="3"
        :value="modelValue"
        @input="handleInput"
        v-bind="$attrs" ></textarea>
        <button class="text-right" @click="$emit('continueClick')">{{buttonText}}</button>
    </div>
</template>

<script>
export default {
    props: {
        modelValue:{
            type: String,
            default: ''
        },
        buttonText: {
            type: String,
            default: 'Ok'
        }
    }, 
    // inheritAttrs:false,
    mounted(){
        // console.log(this.$attrs);
    },
    methods: {
        handleInput(e) {
            this.$emit("update:modelValue", e.target.value);
        }
    },
    beforeUnmount() {
        //alert("Are u sure?");
    },
    unmounted() {
        // alert("Are u sure?");
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

.text-right {
    float: right;
}

textarea {
    padding: 7px 9px;
    margin-bottom: 11px;
    border-radius: 3px;
    width: 100%;
    border: 1px solid gray;
}

.row {
    display: flex;
}

.col-md-6 {
    width: 85%;
}

.shadowed{
    box-shadow: 0 0 3px 2px #111;
}
</style>