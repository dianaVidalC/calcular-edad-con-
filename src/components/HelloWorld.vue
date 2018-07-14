<template lang="pug">
  .hello
    h1 Ingresa tus datos
    input(v-model="name" placeholder="Nombres")
    br
    input(v-model="lastName" placeholder="Apellidos")
    br
    p {{ fullName }}
    input(type="date" v-model="fecha")
    p {{ age }}
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
  
  },
  data(){
    return {
      name: "",
      lastName: "",
      fecha: "",
      edad: ""
    }
  },
  computed:{
    fullName: function () {
      return `${this.name} ${this.lastName}`
    },
    age: function () {
      const birthday = new Date(this.fecha);
      const dateNow = new Date();
    
      if(dateNow.getMonth() + 1< birthday.getMonth() + 1){
           this.edad = dateNow.getFullYear() - birthday.getFullYear() - 1;
      } else if (dateNow.getMonth() + 1 == birthday.getMonth() + 1){
        if(dateNow.getDate()<birthday.getDate()){
          console.log(dateNow.getDate()<birthday.getDate())
            this.edad = dateNow.getFullYear() - birthday.getFullYear() - 1;
        } else {
            this.edad = dateNow.getFullYear() - birthday.getFullYear();
        }
      }else {
          this.edad = dateNow.getFullYear() - birthday.getFullYear();
      }
      if(this.edad) return `Tu edad es: ${this.edad}`;
    }
  }
}
</script>

<style lang="sass" scoped>
  .hello
    text-align: center
    margin-top: 4em
    input
      border: 1px solid #ddd
      border-radius: 5px
      outline: none
      margin-bottom: 1rem
      padding: 7px
    p 
      margin: 1rem
    h1
      font-size: 24px
      font-weight: bold
      margin: 1rem 0
</style>
