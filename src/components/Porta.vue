<template>
  <div class="door-area">
    <div class="door-frame" :class="{ selected: selecionada && !aberta}">
      <vGift v-if="aberta && temPresente"></vGift>
    </div>
    <div class="door" :class="{ open: aberta }"
     @click="selecionada = !selecionada">
      <div class="number" :class="{ selected: selecionada }">{{ numero }}</div>
      <div class="knob" :class="{ selected: selecionada }" @click.stop="aberta = true"></div>
    </div>
  </div>
</template>

<script>
import vGift from "./Gift.vue";
export default {
  name: "vPorta",
  components: { vGift },
  props: {
    numero: {},
    temPresente: { typeof: Boolean },
  },

  data() {
    return {
    aberta: false,
    selecionada: false,
    }
  },
};
</script>

<style>
:root{
  --door-border: 5px solid brown;
  --selected-border: 5px solid yellow;
}

.door-area {
  position: relative;
  width: 200px;
  height: 310px;
  border-bottom: 10px solid #AAA;
  margin-bottom: 20px;

  font-size: 3rem;
  display: flex;
  justify-content: center;
}

.door-frame {
  position: absolute;
  height: 305px;
  width: 180px;
  border-left: var(--door-border);
  border-right: var(--door-border);
  border-top: var(--door-border);
  

  display: flex;
  justify-content: center;
  align-items: flex-end;
}

.door {
  position: absolute;
  top: 5px;
  height: 265px;
  width: 140px;
  background-color: chocolate;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px;
}

.door .knob {
  height: 20px;
  width: 20px;
  border-radius: 10px;
  background-color: brown;
  align-self: flex-start ;
  margin-top: 60px;
}

.door-frame.selected{
  border-left: var(--selected-border);
  border-right: var(--selected-border);
  border-top: var(--selected-border);
}
.door .number.selected{
color: yellow;

}

.door .knob.selected{
  background-color: yellow;
}

.door.open {
  background-color: #0007;
}

.door.open .knob{
  display: none;
}

.door.open .number{
  display: none;
}
</style>