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
    --gift-border-tie: red;
    --gift-border-top: yellow;
    --gift-body: green;
}

.gift {
    position: relative;
    z-index: 40;
    margin-top: 0px;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.gift-top {
    height: 15px;
    width: 80px;
    background-color: var(--gift-border-top);
}

.gift-tie-1 {
    height: 10px;
    width: 80px;
    background-color: var(--gift-border-tie);
    
    position: absolute;
    top:40px;
}

.gift-tie-2 {
    height: 85px;
    width: 10px;
    background-color: var(--gift-border-tie);

    position: absolute;
}

.gift-body {
    height: 70px;
    width: 80px;
    background-color: var(--gift-body);
}
</style>