
<template>
   <div>
    Witaj, {{user}}
    <button @click="logout()">Wyloguj</button><!--rownie dobrze zamiast metody mozna wstawic surowy kod w js-->
   </div>
</template>


<script>
export default {
props: ['userName'],

data() {
     return {
         user : user()
     }
 },
 methods: {
     logout() {
         this.$emit('logout',false);
     },

     user(){
         this.$emit('user',this.user)
     }

 }
}
</script>