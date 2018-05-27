
<template>
   <div>
       <label>Zaloguj się e-mailem</label>
       <input type="email" placeholder = "Podaj swój adres email" v-model="email">
       <button  @click="enter()" >{{buttonLabelToDisplay}}</button>
   </div>
</template>

<script>
export default {
props: ['buttonLabel'],
computed: {
  buttonLabelToDisplay() {
    return this.buttonLabel || 'Zaloguj się ';  
  }
},
 data() {
     return {
         email: ''
     }
 },
 methods: {
     enter() {
         this.$emit('login',this.email);//login odpowiada za wywolania pozniej w App.vue
     },
     mounted() {
        if (!this.buttonLabel) {
        this.buttonLabel = 'Zaloguj się';
        console.log("Value of the buttonLabel is: "+buttonLabel);
  }
  
     }

 }
}
</script>