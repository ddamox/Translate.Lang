<template>
  <div id="translateOutput">  
    <h3> {{translatedText}}</h3>
  </div>
</template>






<script>

export default {

  name: 'translateOutput',
  props: ['translatedText'],
  
  
}
</script>

<style>
#translateOutput{
    text-align: center;
    color: rgb(0, 0, 0);
    position: absolute;
    top: 60%;
    width: 8%;
    display: flex;
    justify-content: center;
    background: #daa520;
    padding: 10px;
    font-family: montserrat;
    font-weight: 600;
    font-size: 18px;
    
}
#translateOutput h3{
    
}

</style>
