<script>
import axios from "axios";
import FlatList from "./FlatList.vue";

export default {
  name: "PrimeiroComponent",
  data() {
    return {
      roupas: [],
    };
  },
  mounted() {
    axios({
      method: "get",
      url: "http://127.0.0.1:8080/api/produtos",
      responseType: "stream",
    })
      .then((res) => {
        this.roupas = JSON.parse(res.data);
      })
      .catch((err) => console.log(err));
  },
  components: { FlatList },
};
</script>

<template>
  <FlatList v-if="this.roupas.length" :roupas="this.roupas" />
</template>
