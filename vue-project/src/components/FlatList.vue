<script>
export default {
  name: "FlatList",
  props: {
    roupas: Array,
  },
};
</script>

<template>
  <div>
    <div v-for="item in roupas" v-bind:key="item.id">
      {{ item.id }} - {{ item.nome }} - {{ item.observacao }} - {{ item.valor }}
    </div>
  </div>
</template>
