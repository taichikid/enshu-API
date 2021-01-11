<template>
  <div class="about">
    <input type="text" maxlength="7">
    <button @click="$router.push({ name: 'Home' })">戻る</button>
    <p>Adress:{{ adressData }}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  props: ["adress"],
  data() {
    return {
      adressData: "",
    };
  },
  async create() {
    let item = await axios.get(
      `https://apis.postcode-jp.com/api/v4/postcodes/${this.adress}?appid=Dd1J4ob9W0NAuKy8W3AqhMMEVvaDCJFFFws7Lkn
`
    );
    this.adressData = item.data.allAdress;
  }
};
</script>
