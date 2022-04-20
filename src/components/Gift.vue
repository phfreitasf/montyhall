<template>
  <div class="gift">
    <div class="gift-tie1"></div>
    <div class="gift-tie2"></div>
    <div class="gift-top"></div>
    <div class="gift-box"></div>
  </div>
</template>

<script>
export default {
  name: 'vGift',
};
</script>

<style>
.gift {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  z-index: 10;
}

.gift-top{
  width: 70px;
  height: 10px;
  background-color: rgb(66, 122, 66);
  border: 2px solid #0004;
}

.gift-box{
  width: 60px;
  height: 50px;
  background-color: rgb(52, 99, 52);
  border: 2px solid #0004;
}

.gift-tie1 {
  position: absolute; 
  width: 10px;
  height: 50px;
  top: 16px;
  background: tomato;
}

.gift-tie2{
  position: absolute;
  top: 35px;
  width: 59px;
  height: 10px;
  background: tomato;
  align-items: center;
}
</style>