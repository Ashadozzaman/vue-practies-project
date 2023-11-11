<template>
  <div>
    <header>
      <h2>{{ msg }}</h2>
    </header>
    <div class="container">
      <div class="tab">
        <div class="tab_menu">
          <div v-for="tab in tabs" :key="tab" class="tab_menu-item" :class="{ 'tab_menu-active': activeTab === tab }"
            @click="activeTab = tab">{{ tab }}</div>
        </div>
      </div>
      <div class="tab_content">
        <br>
        <!-- <Login v-if="activeTab == 'Login'" /> -->
        <keep-alive>
          <component :is="activeTab"></component>
        </keep-alive>
      </div>
    </div>
  </div>
</template>

<script>
import Login from "./Login.vue";
import Register from "./Register.vue";
import Contact from "./Contact.vue";

export default {
  data() {
    return {
      msg: "Dynamic Component",
      tabs: ['Login', 'Register', 'Contact'],
      activeTab: "Login",
      name: 'Ashadozzman Shvou',
      website: 'http://shovoua.com',
      address: 'Dhaka'
    };
  },
  methods: {
    handleClick() {
      //console.log('clicked');
    },
  },
  provide() {
    return {
      name: this.name,
      website: this.website,
      address: this.address,
    }
  },
  components: {
    Login,
    Register,
    Contact,
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
