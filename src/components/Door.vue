<template>
  <div class="door-area">
      <div class="door-frame">
        <gift-vue v-if="which == !open" />
      </div>
      <div class="door">
        <div class="number"></div>
        <div class="knop"></div>
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
      open: false
    }
  }

}
</script>

<style>

:root {
  --border-door: 10px solid blue;
}

.door-area{
  position: relative;
  width: 222px;
 
 
 
  
}
.door-frame{
  position: absolute;
  background-color: brown;
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
  background-color: #444;
  height: 290px;
  width: 200px;

  top: 10px;
  left: 10px;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.knop {
  height: 20px;
  width: 20px;
  background-color: yellow;
  border-radius: 10px;
  align-self: flex-start;
  margin-left: 40px;
  margin-top: 40px;
  z-index: 20;
}

</style>