<template>
  
  <div>
<h1>Hola desde VUE.js 3</h1>
<h2>V-html</h2>
<br>
<div v-html= "html"></div><br>
<hr>


  <h1>V-show</h1>
  <h3>Tu edad es: {{edad}}</h3>
  <h2 v-if="edad >=18 && edad >0 && edad<100">Mayor de edad</h2>
  <h2 v-else-if="edad<18 && edad > 0 && edad <100">Menor de edad</h2>
  <h2 v-else>Edad Invalida</h2>
  <button class="btn btn-primary m-1" @click="inc()">Incrementar</button>
  <button class="btn btn-danger m-1" @click="dis()">Disminuir</button>
  <hr>
  <h1>V-for</h1>
  <ul>
    <li>{{usuarios[0]}}</li>
    <li>{{usuarios[1]}}</li>
    <li>{{usuarios[2]}}</li>
    <li>{{usuarios[3]}}</li>
    <li>{{usuarios[4]}}</li>
  </ul>

  <ul>
    <li v-for="usuario in usuarios" class="text">{{ usuario }}</li>
  </ul>
  <br>
<ul>
<li v-for ="(usuario, index) in usuarios">{{ index }}: {{ usuario }}</li>
</ul>
<br>
<ul>
<li v-for ="(usuario, index) in usuarios" :key="index">{{ index }}: {{ usuario }}</li>
</ul>
<br>
<ul>
<li v-for ="(valor, clave) in uusuarios" :key="clave">{{ clave }}: {{ valor }}</li>
</ul>
<hr />
<h1>v-bind</h1>
<img v-bind:src="url" alt="No hay internet">

<hr />


  <h1>v-on</h1>
<div @dblclick="click" class="contador">clicks: {{clicks}}  </div>
</div>

</template>

<script>
  export default{
    data: () => ({
      titulo: "Hola desde VUE.js",
      html: "<h3> Soy un H3 </h3>",
      edad:0,
      usuarios :["Eunice", "Alberto", "Kevin","Cristopher", "Aldo"],
      clicks: 0,
      url: "https://cdn.svgporn.com/logos/descript-icon.svg"
    }),
    methods:{
    inc(){
      this.edad++;
    },
    dis(){
      this.edad--;
    },
    click() {
    this.clicks++;
  }

  }
  };
</script>

<style scoped>
  *{
    background: aqua;
    margin: 0px;
    align-items: center;
  }
div{
   
    margin: 0.5px 0.5px;
    padding: 100px 50px;
  }
  h2{
    color: tomato;
  }
  .contador{
    background: pink;
    color: black;
    font-weight: bold;
    height: 200px;
  }
</style>
