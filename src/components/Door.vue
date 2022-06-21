<template>
  <div class="door" v-for="door in doors" :key="door.number">
    <div v-if="!door.opened">
      <div class="macaneta" @click="door.opened = !door.opened"></div>
      <div
        class="sub-door"
        @click="door.selected = !door.selected"
        :class="door.selected ? 'selected' : ''"
      >
        <p>{{ door.number }}</p>
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
  border: 3px solid brown;
  height: 350px;
  font-size: 30px;
  text-align: center;
}
.sub-door {
  background-color: silver;
  height: 350px;
  z-index: 1;
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
  background-color: brown;
  z-index: 0;
  position: absolute;
  margin-top: 150px;
}

.selected {
  background-color: rgb(239, 165, 26);
}

.win {
  color: rgb(15, 255, 15);
  display: flex;
  height: 350px;
  justify-content: center;
  align-items: center;
}
</style>