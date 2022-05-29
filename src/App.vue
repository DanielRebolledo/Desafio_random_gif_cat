<template>
  <div>
    <h1>Random Gif Cat</h1>
    <div class="form">
      <form @submit.prevent="obtenerMichi()">
        <div class="input">
          <h4>Título:</h4>
          <input type="text" v-model="title">
        </div>
        
        <div class="input">
          <h4>Filtro:</h4>
          <select name="" v-model="filter">
            <option value="blur">blur</option>
            <option value="mono">mono</option>
            <option value="sepia">sepia</option>
            <option value="negative">negative</option>
            <option value="paint">paint</option>
            <option value="pixel">pixel</option>
          </select>
        </div>
        
        <div class="input">
          <h4>Color:</h4>
          <select name="" v-model="color">
            <option value="green">Verde</option>
            <option value="yellow">Amarillo</option>
            <option value="red">Rojo</option>
            <option value="white">Blanco</option>
          </select>
        </div>
        
        <div class="input">
          <h4>Tamaño:</h4>
          <input type="number" v-model="size">
        </div>
        
        <button type="submit" class="btn">Obtener Michi</button>
      </form>
    </div>
    <img :src="url" class="foto-michi">
    <!-- <img src="https://i.pinimg.com/originals/2a/15/bf/2a15bfef34c0c7e2fd03500bebe11025.gif" class="foto-michi"> -->
  </div>
</template>

<script>


export default {
  name: 'App',
  data: () => ({
    url: '',
    title : 'holi',
    filter: 'blur',
    color: 'green',
    size: '200' 
  }),
  methods: {
      obtenerMichi(){
        this.url = `https://cataas.com/cat/gif/says/${this.title}?filter=${this.filter}&color=${this.color}&size=${this.size}&type=or`
        
      },
  }
}
</script>

<style>
  body{
    padding: 0;
    margin: 0; 
    background-color: #add8e6;
    font-family: Arial, Helvetica, sans-serif;
  }
  
  h1{ 
    text-align: center;
  }
  .form{ 
    padding: 50px 0;
    background-color: #f08080;
  }
  .input{ 
    display: flex;
   justify-content: space-between;
   align-items: center;
  }
  select{ 
    margin: 0;
  }
  form{ 
    width: 80%;
    max-width: 300px;
    margin: auto;
    text-align: center;
    
  }
  .foto-michi{ 
    width: 80%px;
    display: block;
    margin: 50px auto;
    
  }
  input, select{ 
    height: 20px;
    width: 200px;
  }
  .btn{ 
    border: inherit;
    padding: 10px 25px;
    border-radius: 8px;
  }
  .btn:hover{ 
    color: #fff;
    background-color: #f08080;
    border: 1px solid #fff;
  }
</style>
