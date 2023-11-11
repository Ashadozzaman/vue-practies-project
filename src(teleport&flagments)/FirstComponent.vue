<template>
    <h1>This is Component</h1>
    <span>Name: {{name}}</span><br>
    <span>Phone: {{phone}}</span><br>
    <span>website: {{websiteAddress}}</span><br>
</template>

<script>
export default {
    props:{
        name:{
            type:String,
        },
        phone:{
            type: String,
            required: true,

        },
        websiteAddress:{
            type: String,
            default: "http://yourwebsite.com",
        },
    },
    data(){
        return {
            
        }
    }
}
</script>