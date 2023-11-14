<template>
  <div>
    <header>
      <h2>{{ msg }}</h2>
    </header>
    <div class="container">
      <input 
        type="text" 
        v-model="name" 
        placeholder="enter your name"
        ref="inputName"
      >
      <the-comment v-model="comment" placholder="enter comment" ref="commentInput"></the-comment>
    </div>
  </div>
</template>

<script>
import TheComment from "./TheComment.vue";

export default {
  data() {
    return {
      msg: "Working with references",
      name: 'Ashadozzman Shvou',
    };
  },
  methods: {
    handleClick() {
      //console.log('clicked');
    },
  },
  mounted() {
    console.log(this.$refs.commentInput);
  },
  components: {
    TheComment,
  }
};
</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

ul {
  margin-left: 22px;
}

body {
  font-family: sans-serif;
  line-height: 1.8;
}

header {
  background-color: #1f2c46;
  color: #41b883;
  font-size: 22px;
  padding: 22px;
  text-align: center;
}

.tab_content {
  padding: 0 5%;
  background-color: antiquewhite;
  margin: 0 5%;
}

.tab_menu {
  display: flex;
  padding: 0 5%;
}

.tab_menu-active {
  background-color: rgb(97, 97, 226) !important;
}

.tab_menu-item {
  padding: 6px 15px;
  background-color: rgb(160 200 246);
}

input {
  padding: 5px 11px;
  margin-bottom: 11px;
}
</style>
