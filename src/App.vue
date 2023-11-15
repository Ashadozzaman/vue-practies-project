<template>
  <div>
    <header>
      <h2>{{ msg }}</h2>
    </header>
    <div class="container">
      <h1>User Registration</h1>
      <label>Full Name</label><br>
      <input type="text" v-model="formData.fullname" placeholder="enter your name" />
      <br />
      <label>About You</label><br>
      <textarea name="aboutYou" v-model="formData.aboutYou" id="" rows="5"></textarea>
      <br>
      <label>Gender</label> <br/>
      <label><input type="radio" name="gender" value="M"  v-model="formData.gender"> Male</label>
      <label><input type="radio" name="gender" value="F" class="ml-2" v-model="formData.gender"> Fe-Male</label>
      <label><input type="radio" name="gender" value="O" class="ml-2" v-model="formData.gender"> Others</label>
      <br>
      <label> Laguage </label><br>
      <select name="language" id="" v-model="formData.language">
        <option value="">--Select Option--</option>
        <option v-for="(value,key) in languageLists" :key="key" :value="value">{{ key }}</option>
      </select>
      <br>
      <label> Skills </label><br>
      <select name="skills" multiple v-model="formData.skills">
        <option value="">--Select Option--</option>
        <option value="HTML">HTML</option>
        <option value="CSS">CSS</option>
        <option value="PHP">PHP</option>
        <option value="JAVA">JAVA</option>
        <option value="Laravel">Laravel</option>
      </select>
      <br>
      <label for="">Agreement</label>
      <br/>
      <label><input type="checkbox" name="agreement" v-model="formData.agreement"> I Agree to the Terms and Services</label>
      <br>
      <label for="">Social Account</label>
      <br/>
      <label><input type="checkbox" name="agreement" v-model="formData.socials" value="fb"> Facebook</label>
      <label><input type="checkbox" name="agreement" v-model="formData.socials" value="tw"> Twiter</label>
      <label><input type="checkbox" name="agreement" v-model="formData.socials" value="go"> Google</label>
      
      <hr />
      <div v-for="(value, key) in formData">
        <strong>{{ key }} : </strong> {{ value }}
      </div>
    </div>
  </div>
</template>

<script>
import TheComment from "./TheComment.vue";

export default {
  data() {
    return {
      msg: "Working with Form",
      name: '',
      formData: {
        fullname: "",
        aboutYou: "",
        gender : "F",
        language : "",
        skills : "",
        agreement: false,
        socials: [],
      },
      languageLists:{
        Bangla: 'bn',
        English: 'en',
        Spenish: 'es',
      }
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

.container {
  padding: 5px;
}
.ml-2{
  margin-left: 10px;
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
  border: 2px solid black;
}

textarea {
  padding: 5px 11px;
  margin-bottom: 11px;
  border: 2px solid black;
  width: 50%;
}
</style>
