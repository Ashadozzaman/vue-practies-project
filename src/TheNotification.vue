<template>
  <teleport to='#notification'>
    <div class="the-notification">
        {{ text }}
    </div>
  </teleport>
</template>

<script>
export default {
    props: ['text']
}
</script>

<style>
.the-notification{
    width: 200px;
    border: 1px solid gray;
    box-shadow: 0 0 8px 2px rgba(0, 0, 0, 0.5);
    color: rgb(192, 117, 26);
    background-color: #fff;
    padding: 2px;
    margin: 2px;
}
</style>