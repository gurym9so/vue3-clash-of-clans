<template>
  <div class="md-body">
    <div class="card__wrapper" v-for="item in items" :key="item.id">
      <Card
        :name="`${item.lvl} lvl`"
        :title="item.title"
        :imgUrl="item.img"
        :link="`/${item.alias}`"
      >
        <template v-slot:body>
          {{ item.descr }}
        </template>
        <template v-slot:footer> </template>
      </Card>
    </div>
  </div>
</template>

<script>
import Card from "@/components/UI/Card";
import items from "@/seeders/items.js";

export default {
  components: { Card },
  data() {
    return {
      items: items,
    };
  },
};
</script>
