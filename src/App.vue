<template>
  <div id="app">
    <form>
      <div>
        <label>Título de la tarjeta: </label>
        <select v-model="tituloTarjeta">
        <option value="Tarjeta de Crédito">VISA Classic Crédito</option>
        <option value="Tarjeta de Débito">VISA Gold Crédito</option>
        <option value="Tarjeta de Débito">VISA Platinum Crédito</option>
        <option value="Tarjeta de Débito">VISA Signature Crédito</option>
      </select>
      </div>

      <div>
        <label>Chip SRC: </label>
        <input v-model="chipSRC" placeholder="/chip.png" />
      </div>

      <div>
        <label>Número: </label>
        <input v-model="numero" maxlength="16"/>
      </div>

      <div>
        <label>Fecha de expiración: </label>
        <input v-model="fechaExpiracion" />
      </div>

      <div>
        <label>Propietario: </label>
        <input v-model="propietario" />
      </div>

      <div>
        <label>Tipo de tarjeta SRC: </label>
        <input v-model="tipoTarjetaSRC" placeholder="/visa.png" />
      </div>
    </form>

    <div class="carnet">
      <h3>{{ tituloTarjeta }}</h3>
      <img width="40" :src="chipSRC" alt="" />
      <div>
        <h2>{{ numero }}</h2>
        <span>Fecha Exp: <b>{{ fechaExpiracion }}</b></span>
      </div>
      <footer>
        <span>{{ propietario }}</span>
        <img :src="tipoTarjetaSRC" width="60" />
      </footer>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      tituloTarjeta: "",
      chipSRC: "",
      numero: "",
      fechaExpiracion: "",
      propietario: "",
      tipoTarjetaSRC: ""
    }
  }
}
</script>

<style>
* {
  margin: 0;
}

body {
  background-image: url("./../public/background.jpg");
  background-repeat: no-repeat ;
  background-size: cover;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  font-size: 10px;
  font-family: sans-serif;
}

#app {
  display: flex;
  gap: 40px;
}

form {
  padding: 18px;
  border-radius: 20px;
  border: ridge 1px;
  box-shadow: 1px 1px 1px 1px gray;
  font-weight: bold;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
  background: white;
}

form div {
  display: grid;
  grid-template-columns: 100px 200px;
  align-items: center;
  gap: 5px;
}

form div label {
  text-align: right;
}

.carnet {
  width: 400px;
  height: 230px;
  color: white;
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background: rgba(1, 19, 43, 0.5);
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.4);
  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  border-radius: 10px;
  border: 1px solid rgba(255, 255, 255, 0.18);


}

h3 {
  font-size: 20px;
}

h2 {
  font-size: 30px;
  letter-spacing: 10px;
  margin-bottom: 15px;
  text-shadow: 0px 0px 1px gold;
  font-family: Times;
}

b {
  font-size: 16px;
}

footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  font-weight: bold;
  font-size: 18px;
  text-transform: uppercase;
  font-style: italic;
}
</style>
