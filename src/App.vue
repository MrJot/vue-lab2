  <template>
    <div id="app">
      <!-- <img src="./assets/logo.png"> -->
      <h1>Witaj w systemie do zapisów za zajęcia</h1>
     
      <div v-if="!isAutenticated">Zalogu sie emailem: 
      <input type="email" v-model="email">
      <button @click="logIn()">Zaloguj</button>
      </div>
      
      <div v-else>
        Witaj, {{email}}     
        <button @click="logOut()">wyloguj</button>
      </div>
  
      <!-- <div v-if="email.length < 10">Ale masz krótki adres!</div>
      <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
      <div v-else>Twój adres e-mail jest stanowczo za długi.</div> -->
      <!--  -->
      <!-- <h2>Essential Links</h2>
      <ul>
        <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
        <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
        <li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
        <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
      </ul>
      <h2>Ecosystem</h2>
      <ul>
        <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
        <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
        <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
        <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
      </ul> -->
    </div>
  </template>

  <script>
export default {
  name: "app",
  data() {
    return {
      email: "",
      isAutenticated: false
    };
  },
  methods: {
    alertMyEmail() {
      alert(this.email);
    },
    logIn() {
      this.isAutenticated=true
    },
    logOut(){
      this.isAutenticated=false
    }
  }
};
</script>





  <style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
