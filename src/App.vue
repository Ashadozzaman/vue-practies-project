<template>
  <div>
    <h1>{{ msg }}</h1>
    <div class="container">
      <the-comment v-model="myComment"
      buttonText="Continue"
      class="shadowed"
      placeholder="Enter Comment"
      @click="handleClick" 
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
    };
  },
  methods: {
    handleClick(){
      console.log('clicked');
    }
  },
  components: {
    TheComment
  }
};
</script>
