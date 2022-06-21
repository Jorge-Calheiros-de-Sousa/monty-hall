<template>
  <div class="montyhall">
    <Title title="O problema de Monty Hall" />
    <div class="container">
      <div class="formulario" v-if="!startGame">
        <div class="container-input">
          <span>Digite o numero maximo de portas: </span
          ><input type="text" v-model="maxDoors" class="input" />
        </div>
        <div class="container-input">
          <span>Digite a porta premiada: </span
          ><input type="text" v-model="priveDoor" class="input" />
        </div>
        <button class="button" @click="changeStatusGame">Iniciar</button>
      </div>
      <div v-if="startGame">
        <div class="formulario">
          <button class="button" @click="changeStatusGame">Voltar</button>
        </div>
        <div class="game">
          <Door :doors="Doors" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Title from "../components/Title.vue";
import Door from "../components/Door.vue";
export default {
  components: { Title, Door },
  data: function () {
    return {
      startGame: false,
      Doors: [],
      maxDoors: 8,
      priveDoor: 1,
    };
  },
  methods: {
    changeStatusGame() {
      this.startGame = !this.startGame;
      this.Doors = [];
      this.changeDoors();
    },
    changeDoors() {
      for (let index = 0; index < this.maxDoors; index++) {
        const number = index + 1;
        if (this.priveDoor == number) {
          this.Doors.push({
            number: number,
            prive: true,
            selected: false,
            opened: false,
          });
        } else {
          this.Doors.push({
            number: number,
            prive: false,
            selected: false,
            opened: false,
          });
        }
      }
    },
  },
};
</script>

<style>
.container {
  width: 100%;
  margin-left: auto;
  margin-right: auto;
  text-align: center;
}
.container-input {
  margin-top: 10px;
  color: white;
}
.input {
  width: 25px;
  font-size: 18px;
}
.button {
  padding: 0 5px 0 5px;
  font-size: 18px;
  cursor: pointer;
}
.game {
  justify-content: space-around;
  align-self: stretch;
  flex-wrap: wrap;
  display: flex;
  margin-top: 10px;
}
</style>