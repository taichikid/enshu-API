<template>
  <div class="home">
    <input type="text" maxlength="7" v-model="adress">
    <button @click="$router.push({ name: 'About', params: { adress: adress} })">住所自動入力</button>
    <p>Adress:</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      adrees: ""
    };
  }
};
</script>
