<template>
  <div class="the-card">
     <div class="the-card_title">
        {{cardTitle}}
     </div>
     <div class="the-card_body">
        <slot></slot>
     </div>
     <div class="the-card_footer">
        <slot name="footer" v-if="$slots.footer">
            Default Footer
        </slot>
     </div>
  </div>
</template>

<script>
export default {
    mounted(){
        console.log(this.$slots.footer);
    },
    props: ['cardTitle']
}
</script>

<style>
.the-card{
    width:200px;
    border: 1px solid #006f88;
    min-height: 100px;
    margin: 22px auto;
}
.the-card_title{
    background: #167db1;
    padding: 5px 11px;
    color:#fff;
}
.the-card_body{
    padding: 11px;
}


.the-card_body img{
    height: 111px;
}
.the-card_footer{
    background: #6c7273;
    text-align: center;
    padding: auto;
}

</style>