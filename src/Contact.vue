<template>
    <div>
        <p>Contact Details</p>
        <p><strong>Name:</strong> {{ name }}</p>
        <p><strong>Website:</strong> {{ website }}</p>
        <p><strong>Address:</strong> {{ address }}</p>
    </div>
</template>

<script>
export default {
    inject:['name','website','address'],
    props:{
        // name: {
        //     type: String
        // },
        // website: {
        //     type: String,
        //     required: false,
        //     default: "http://shovoua.com"
        // },
        // address:{
        //     type: String,
        //     required: true
        // }
    },
    data() {
        return {
        }
    },
}
</script>

<style>
button{
    padding: 5px;
    margin-bottom: 5px;
}

</style>