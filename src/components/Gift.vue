<template>
    <div class="gift">
        <div class="gift-top"></div>
        <div class="gift-tie-1"></div>
        <div class="gift-tie-2"></div>
        <div class="gift-body"></div>
    </div>
</template>

<script>
export default {
    name: 'AllGift'
}
</script>

<style>
:root {
    --gift-border-tie: rgb(184, 17, 17);
    --gift-border-top: rgb(26, 26, 26);
    --gift-body: green;
}

.gift {
   position: relative;
}

.gift-top {
  position: absolute;
  
  z-index: 10;
  width: 105px;
  height: 25px;
  background-color: var(--gift-border-top);
  border: 1px solid black;

}

.gift-tie-1 {
 position: absolute;
 
 z-index: 20;
 width: 100px;
 height: 20px;
 top: 50px;

 background-color: var(--gift-border-tie);

}

.gift-tie-2 {
 position: absolute;
 
 z-index: 5;
 width: 20px;
 height: 100px;
 

 background-color: var(--gift-border-tie);

}

.gift-body {
   width: 100px;
   height: 100px;
   background-color: var(--gift-body);
  
   position: absolute;

  

}
</style>