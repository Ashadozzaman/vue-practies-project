<template>
  <div>
    <h1>{{ msg }}</h1>
    <button @click="hide = true">Hide</button>
    <div class="container">
      <the-comment v-model="myComment"
      buttonText="Continue"
      class="shadowed"
      placeholder="Enter Comment"
      @click="handleClick"
      v-if="!hide" 
      ></the-comment>
      <hr>
      <p>{{myComment}}</p>
    </div>
  </div>
</template>

<script>
import TheComment from "./TheComment.vue";

export default {
  data() {
    return {
      msg: "Vue Non-Prop",
      myComment: "Mr.",
      hide:false,
    };
  },
  methods: {
    handleClick(){
      console.log('clicked');
    }
  },
  created() {
    console.log('created');
  },
  mounted() {
    console.log('mounted');
  },
  beforeMount() {
    console.log('beforeMount');
  },
  updated() {
    console.log('updated');
  },
  components: {
    TheComment
  }
};
</script>
