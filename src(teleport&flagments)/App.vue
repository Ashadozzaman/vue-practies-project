<template>
  <div>
    <h1>{{ msg }}</h1>
    <div class="container">
      <the-comment v-model="myComment"
      buttonText="Continue"
      class="shadowed"
      placeholder="Enter Comment"
      @click="handleClick"
      @continueClick="handleContinueClick"
      ></the-comment>
      <hr>
      <p>{{myComment}}</p>
      <button @click="showNotification">Show Notification</button>
      <the-dialog heading="Are You Sure?" v-if="showDialog">
        <p>
          Are you realy want to comment?
          <br>
          <button @click="showDialog = false">Yes</button>
          <button>NO</button>
        </p>
      </the-dialog>
      <the-notification
      v-for="(n,i) in notifications"
      :key="i"
      :text="n"
      ></the-notification>
    </div>
  </div>
</template>

<script>
import TheComment from "./TheComment.vue";
import TheDialog from "./TheDialog.vue";
import TheNotification from "./TheNotification.vue";

export default {
  data() {
    return {
      msg: "Vue Non-Prop",
      myComment: "Mr.",
      showDialog: false,
      notifications:[],
    };
  },
  methods: {
    handleClick(){
      //console.log('clicked');
    },
    handleContinueClick(){
      console.log('clcik');
      this.showDialog = true;
    },
    showNotification(){
      this.notifications.push('You have a notification');
      setTimeout( () => {
        this.notifications.shift();
      }, 2000)
    }
  },
  components: {
    TheComment,
    TheDialog,
    TheNotification
  }
};
</script>
