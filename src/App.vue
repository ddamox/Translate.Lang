<template>
  <div id="app">
     
     <h1> A Word Translation Application </h1>
     <div class="css-typing">
        <p>This is a simple word translation application</p>
        <p>It can translate word from one language to another</p>
        <p>It is powered by the yandex.translate api</p>
        <p>Built with Vue.Js</p>  
     </div>
     <translateForm v-on:formSubmit = "translateText"></translateForm>
     <translateOutput v-text="translatedText"></translateOutput>
     <div class="footer"> <button><a href="http://"> The Documentation </a></button> Developed by Damilola Shofoluwe &nbsp; &nbsp;
       <img src="./assets/madebydammy1.png" alt="" srcset=""> &nbsp; <fa prefix="fab" icon="faTwitter"/>

     </div>
     <svg viewBox="0 0 3387 1270">
  <path id="planePath" class="planePath" d="M-226 626c439,4 636,-213 934,-225 755,-31 602,769 1334,658 562,-86 668,-698 266,-908 -401,-210 -893,189 -632,630 260,441 747,121 1051,91 360,-36 889,179 889,179" />
  <g id="plane">
    <polygon class="fil1" points="-141,-10 199,0 -198,-72 -188,-61 -171,-57 -184,-57 " />
    <polygon class="fil2" points="199,0 -141,-10 -163,63 -123,9 " />
    <polygon class="fil3" points="-95,39 -113,32 -123,9 -163,63 -105,53 -108,45 -87,48 -90,45 -103,41 -94,41 " />
    <path class="fil4" d="M-87 48l-21 -3 3 8 19 -4 -1 -1zm-26 -16l18 7 -2 -1 32 -7 -29 1 11 -4 -24 -1 -16 -18 10 23zm10 9l13 4 -4 -4 -9 0z" />
    <polygon class="fil1" points="-83,28 -94,32 -65,31 -97,38 -86,49 -67,70 199,0 -123,9 -107,27 " />
  </g>
  <!-- Define the motion path animation -->
  <animateMotion xlink:href="#plane" dur="5s" repeatCount="indefinite" rotate="auto">
    <mpath xlink:href="#planePath" />
  </animateMotion> 
</svg>
  </div>
</template>






<script>
import translateForm from './components/translateForm'
import translateOutput from './components/translateOutput'

export default {
  name: 'App',
  data: function (){
    return {
      translatedText: ''
    }
  },
  components: {
    translateForm,
    translateOutput
  },
  methods: {

    translateText:function(text, language) {
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180806T233847Z.704ac4f55e78d0df.4646bc3744c15b55b18589ad22dff2ad411056c2&lang='+language+'&text='+text).then((response) => {
      this.translatedText = response.body.text[0];
        
      } ) ;  // the request to the yandex api
      
    }

  }
}
</script>





















<style>
#app {
  padding: 0;
  margin-top: -21px;
  margin-left: -8px;
  width: 101.2%;
  height: 102vh;
  background: #000000;
  font-family: montserrat, raleway;
  display: flex;
  flex-direction: column;
  align-items: center;
}
#app h1{
  color: #DAA520;
  text-align: center;
  padding-top: 25px;
  font-weight: 300;
  z-index: 100;
}


.css-typing{
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  top: 13vh;

  position: absolute;
  z-index: 150;
}
.css-typing p {
  /*font-family: "Courier";*/
  font-size: 14px;
  width: 22em;
  color: #ffffff;
  white-space: nowrap;
  overflow: hidden;
  -webkit-animation: type 4s steps(63, end);
  animation: type 4s steps(53, end);
  border-right: .15em solid #DAA520;
  margin-bottom: -10px;
}

.css-typing p:nth-child(2) {
  
  width: 26em;
  white-space: nowrap;
  overflow: hidden;
  opacity: 0;
  -webkit-animation: type 4.5s steps(40, end);
  animation: type2 4.5s steps(50, end);
  -webkit-animation-delay: 4s;
  animation-delay: 4s;
  -webkit-animation-fill-mode: forwards;
  animation-fill-mode: forwards;
  color: #DAA520;
    border-right: .15em solid #ffffff;


}


.css-typing p:nth-child(3) {
  white-space: nowrap;
  overflow: hidden;
  width: 20.6em;
  opacity: 0;
  -webkit-animation: type 4s steps(20, end);
  animation: type3 4s steps(20, end);
  -webkit-animation-delay: 8s;
  animation-delay: 8s;
  -webkit-animation-fill-mode: forwards;
  animation-fill-mode: forwards;
}
.css-typing p:nth-child(4) {
  width: 9em;
  white-space: nowrap;
  overflow: hidden;
  opacity: 0;
  -webkit-animation: type 1s steps(40, end);
  animation: type4 1s steps(50, end);
  -webkit-animation-delay: 12s;
  animation-delay: 12s;
  -webkit-animation-fill-mode: forwards;
  animation-fill-mode: forwards;
  color: #DAA520;
    border-right: .15em solid #ffffff;
}
@keyframes type {
  from {width: 0;}
}
@keyframes type2 {
  0% { width: 0;}
  1% {opacity: 1;}
  100% {opacity: 1;}
}
@keyframes type3 {
  0% {width: 0;}
  1% {opacity: 1;}
  100% {opacity: 1;}
}
@keyframes type4 {
  0% {width: 0;}
  1% {opacity: 1;}
  100% {opacity: 1;}
}

.planePath {
  stroke: #D9DADA;
  stroke-width: .1%;
  stroke-width: .5%;
  stroke-dasharray: 1% 2%;
  stroke-linecap: round;
  fill: none;
  opacity: 0.07;
}

.fil1 {
  fill: #D9DADA;
  opacity: 0.1;
}

.fil2 {
  fill: #C5C6C6;
    opacity: 0.1;

}

.fil4 {
  fill: #9D9E9E;
    opacity: 0.1;

}

.fil3 {
  fill: #AEAFB0;
    opacity: 0.1;

}

translateOutput {
  
}

.footer{
  z-index: 500;
  position: absolute;
  top: 89vh;
  color: #ffffff;
  width: 100%;
  height: 010vh;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 10px;
  font-weight: 300;
  letter-spacing: 1px;
}

img{
  width: 100px;
  margin-top: -30px;

}

button{
  margin-right: 200px;
  padding: 10px;
}
button a{
  text-decoration: none;
  color: #DAA520;
  padding: 25px 20px;
}

button:hover, a:hover{
  background: #000000;
  border: 1px solid #000000;
  text-decoration: underline;
}
</style>
