
<template>
   <div>
    <h1>Logowanie zakończone sukcesem</h1>
    Witaj,{{this.$parent.authenticatedUsername}}<br>

    <button @click="logout()">Wyloguj</button><!--rownie dobrze zamiast metody mozna wstawic surowy kod w js-->
    <meeting-page></meeting-page>
   </div>
   
</template>


<script>
import MeetingPage from "./meetings/MeetingPage.vue";
export default {
    components: {
      MeetingPage},
props: ['authenticatedUsername'],

data() {
     return {
     }
 },
 methods: {
     logout() {
         this.$emit('logout',false);
     },



 }
}
</script>