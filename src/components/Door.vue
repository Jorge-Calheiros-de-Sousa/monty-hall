<template>
  <div
    class="door"
    :class="door.selected ? 'selected' : ''"
    v-for="door in doors"
    :key="door.number"
  >
    <div v-if="!door.opened">
      <div class="sub-door" @click="door.selected = !door.selected">
        <p class="number">{{ door.number }}</p>
        <div
          class="macaneta"
          @click.stop="door.opened = !door.opened"
          :class="door.selected ? 'yellow' : ''"
        ></div>
      </div>
    </div>
    <div v-if="door.opened">
      <div v-if="door.prive">
        <span class="win">Ganhou</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    doors: {},
  },
};
</script>

<style>
.door {
  background-color: transparent;
  border: 3px solid #993430;
  height: 350px;
  width: 200px;
  font-size: 30px;
  text-align: center;
  border-bottom: 5px solid gray;
}
.sub-door {
  background-color: #c66d33;
  height: 350px;
  z-index: 1;
  padding: 20px;
  box-sizing: border-box;
}
.sub-door p {
  margin: 0;
}

.macaneta {
  width: 20px;
  height: 20px;
  border-radius: 100%;
  margin-left: 10px;
  cursor: pointer;
  background-color: #993430;
  margin-top: 130px;
}

.yellow {
  background-color: yellow;
}

.selected {
  border-color: yellow;
  color: yellow;
}

.win {
  color: rgb(15, 255, 15);
  display: flex;
  height: 350px;
  justify-content: center;
  align-items: center;
}
</style>