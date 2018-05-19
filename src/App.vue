    <template>
      <div id="app">
        <!-- <img src="./assets/logo.png"> -->
        <h1>Witaj w systemie do zapisów za zajęcia</h1>
      
        <div v-if="!isAutenticated">Zalogu sie emailem: 
        <input type="email" v-model="email">
        <button @click="toggle()">Zaloguj</button>
        </div>
        
        <div v-else>
          Witaj, {{email}}     
          <button @click="toggle()">wyloguj</button><!--rownie dobrze zamiast metody mozna wstawic surowy kod w js-->
        </div>
    
        <!-- <div v-if="email.length < 10">Ale masz krótki adres!</div>
        <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
        <div v-else>Twój adres e-mail jest stanowczo za długi.</div> -->
      </div>
    </template>

    <script>
  export default {
    name: "app",
    data() {
      return {
        email: "Podaj swoj adres email..",
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
      },

      toggle(){
        this.isAutenticated = !this.isAutenticated;
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
