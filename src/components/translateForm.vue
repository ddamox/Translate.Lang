<template>
  <div id="translateForm">  
    <form v-on:submit = "formSubmit">

        <input type = "text" v-model = "textToTranslate" placeholder="Enter a word..."> 
        <select v-model="language">
            <option value="ru"> Russian </option> <option value="zh"> Chinese </option> <option value="ar"> Arabic </option>
            <option value="nl"> Dutch </option> <option value="el"> Greek </option> <option value="he"> Hebrew </option>
            <option value="pt"> Portugese </option> <option value="es"> Spanish </option> <option value="fr"> French </option>
            <option value="la"> Latin </option> <option value="Ge"> German </option> 
        </select>
        <input type="submit" value="Translate">

    </form>
  </div>
</template>






<script>

export default {
  name: 'translateForm',
  data() {
      return {
          textToTranslate: '',
          language: ''
      }
  },
  created (){

      this.language = 'ru' //default language

  },
  methods: {
      formSubmit(e){

          this.$emit('formSubmit', this.textToTranslate, this.language) // this is to emit anything we type into the input to the main app
          e.preventDefault();
          
      }
  }
  
}
</script>

<style>
#translateForm{
    color: #fff;
}
form{
    width: 100%;
    position: absolute;
    top: 44vh;
    display: flex;
    justify-content: center;
    left: 0;
}
form input[type= text]{
    
    
    border: none;
    color: #daa520;
    outline: none;
    height: 50px;
    width: 25%;
    background: #a8a4a454;
    -moz-box-shadow:    inset 0 0 4px #000000;
   -webkit-box-shadow: inset 0 0 4px #000000;
   box-shadow:         inset 0 0 4px #000000;
   padding: 2px;
   font-size: 14px;
}
 ::-moz-placeholder, ::-webkit-input-placeholder{

    color: #daa520;
}

select{
       
    background: #a8a4a454;
    border: none;
    outline: none;
    color: #daa520;
    padding-left: 15px;
    padding-right: 5px;
    font-size: 14px;
}


option {
    border: none;
    outline: none;
    padding-right: 15px;
}
input[type = submit]{
    background: #daa520;
    color: rgb(46, 45, 45);
    padding-left: 25px;
    padding-right: 25px;
    font-family: montserrat;
    border:none;
    outline: none;
    cursor: pointer;
    font-size: 14px;

}
input[type = submit]:hover{
    color: #000;
    background: #6d4e02;
    
}
@media (max-width: 600px){

    #translateForm {
        width: 90%;
        display: flex;
        justify-content: center;
        margin: 0;
        
    }

    form{
        width: 90%;
        display: flex;
        justify-content: center;
        left: 6.2%;
        top: 40vh;
    }
    form input[type= text]{
        height: 35px;
        width: 30%;
        font-size: 10px;
    }
    select{
        font-size: 10px;
        padding-left: 10px;
        padding-right: 10px;
    }
    option{
        padding-right: 15px;
    }
    input[type = submit]{
        font-size: 10px;
    }
}
</style>
