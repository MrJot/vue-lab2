    <template>
      <div>
        
        <div v-if = "!isAutenticated">
        <login-form @login="logMeIn($event)" > </login-form>
        </div>
        <div v-else>
           <after-login @logout = logOut($event) @user = {{authenticatedUsername}}>  </after-login>
        </div>
      </div>
    </template>

  <script>
  import "milligram";
  import LoginForm from "./LoginForm.vue";
  import AfterLogin from "./AfterLogIn.vue";
  export default {
    components: {
      LoginForm,
      AfterLogin
      },
    name: "app",
    data() {
      return {
        // email: "",
        isAutenticated: false,
      };
    },
    methods: {
      alertMyEmail() {
        alert(this.email);
      },

      toggle(){
        this.isAutenticated = !this.isAutenticated;
        console.log("I am inside toggle() function");
      },

      
      logMeIn(username) {
      this.isAutenticated = !this.isAutenticated;
      this.authenticatedUsername = username;
      console.log("I am inside logMeIn fuction. UserName is: " + this.authenticatedUsername);
},
      logOut(status){
        this.isAutenticated = status;
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
    font-weight: big;
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
