<template>
  <div class="door-area">
      <div class="door-frame" :class="{selected: selected && !open}">
        <gift-vue v-if="open && which" />
      </div>
      <div class="door" :class="{open}" @click="selected = !selected">
        <div class="number"></div>
        <div class="knop" :class="{selected}" @click.stop="open = true"></div>
      </div>
  </div>
</template>

<script>
import GiftVue from './Gift.vue'

export default {
  name: 'AllDoor',
  components: { GiftVue },
  props: {
    number: {},
    which: {type: Boolean}
  },
  data: function() {
    return {
      open: false,
      selected: true
    }
  }

}
</script>

<style>

:root {
  --border-door: 10px solid rgb(90, 90, 23);
  --border-selected: 10px solid rgb(255, 197, 8);

  --closed-door: rgb(126, 88, 18);
  --open-door: #444;
}

.door-area{
  position: relative;
  width: 222px;

}
.door-frame{
 
  background-color: var();
  height: 300px;
  width: 220px;
  z-index: 10;

  border-bottom: 10px solid #fff;

  border-top: var(--border-door);
  border-right: var(--border-door);
  border-left: var(--border-door);

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end;
  
}
.door {
  position: absolute;
  border-bottom: 10px solid #fff;
  background-color: var(--closed-door);
  height: 290px;
  width: 183px;
  top: 10px;
  z-index: 10;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

}

.knop {
  height: 20px;
  width: 20px;
  background-color:  rgb(61, 61, 61);
  border-radius: 10px;
  align-self: flex-start;
  margin-left: 40px;
  margin-top: 40px;
  z-index: 20;
}
.door-frame.selected{
  border-top: var(--border-selected);
  border-right: var(--border-selected);
  border-left: var(--border-selected);
}

.door > .knop.selected {
  background-color: var();
}
.door.open{
  background-color: rgb(61, 61, 61);
  z-index: -10;
}

</style>