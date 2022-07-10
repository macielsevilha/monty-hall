<template>
    <div id="app">
        <div class="header">
            <h1>Problema do Monty Hall</h1>
            <form action="">
                <label for="portsAmount">Quantas portas?</label>
                <input type="text" id="portsAmount" v-model.number="portsAmount" name="portsAmount" size="3">
                <label for="firstPort">Qual a porta premiada?</label>
                <input type="text" name="firstPort" size="3"> <br />
                <button v-if="!started" @click="started = true">Iniciar</button> <br />
                <button v-if="started"  @click="started = false">Reinicar</button>
                <div class="doors" v-if="started">
                  <div v-for="i in portsAmount" :key="i">
                    <door-vue :which="i === selectedPort" :number="i" />
                  </div>
                </div>
            </form>
           
        </div>
    </div>
</template>

<script>
import DoorVue from './components/Door.vue'

export default {
    name: 'App',
    components: {DoorVue},
    data: function() {
       return {
        started: false,
        portsAmount: 3,
        selectedPort: null
       }
      
    }
   
}

</script>

<style>
:root {
    --border-first: green;
}

@font-face {
    font-family: 'RobotoMono';
    src: url('./fonts/RobotoMono-Thin.ttf');
}

* {
    box-sizing: border-box;
}

body {
    font-family: 'RobotoMono';
    font-weight: bolder;
    background-image: radial-gradient(circle at 99.78% 21.26%, #a6f0be 0, #96ebbf 12.5%, #7ee3bc 25%, #5dd6b5 37.5%, #1fc5ab 50%, #00b4a3 62.5%, #00a79f 75%, #009ea0 87.5%, #0098a5 100%);
    height: 100vh;
}

#app {
    padding: 30px;
    text-align: center;

}

#app form label {
    padding: 10px;
}

#app form input {
    height: 30px;
    width: 80px;
    border: 2px solid var(--border-first);

}
.doors {
  display: flex;
  justify-content: center;
   flex-wrap: wrap;
}
.doors div{
   display: flex;
   align-self: stretch;
   justify-content: space-around;
  
    margin: 10px;
}
</style>