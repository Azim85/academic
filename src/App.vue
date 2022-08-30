<template>
  <div class="container" style="height: 80vh">
    <div class="header">
      <h1 class="text-center">Fargona academik litseyi</h1>
      <p>
        Jami o'zbek tili yo'nalishidagi o'g'il bola talabalar:
        {{ data.length }} ta
      </p>
      <div class="search">
        <input type="text" v-model="search" />
      </div>
    </div>
    <div
      class="table-responsive"
      style="overflow-x: auto; overflow-y: auto; height: 100%"
    >
      <table class="table position-relative">
        <thead>
          <tr class="position-sticky text-white">
            <th
              scope="col"
              class="position-sticky top-0 bg-dark border text-center"
              v-for="h in head"
              :key="h"
            >
              {{ h }}
            </th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(d, i) in data" :key="d.id_raqami" class="border">
            <td>{{ i + 1 }}</td>
            <td>{{ d.otm_nomi }}</td>
            <td>{{ d.talim_shakli }}</td>
            <td>{{ d.talim_yonalishi }}</td>
            <td>{{ d.talim_tili }}</td>
            <td>{{ d.FIO }}</td>
            <td>{{ d.Jinsi }}</td>
            <td>{{ d.id_raqami }}</td>
            <td>{{ d.kitob_raqami }}</td>
            <td>{{ d.fan1 }}</td>
            <td>{{ d.FIELD11 }}</td>
            <td>{{ d.FIELD12 }}</td>
            <td>{{ d.Fan2 }}</td>
            <td>{{ d.FIELD14 }}</td>
            <td>{{ d.FIELD15 }}</td>
            <td>{{ d.Fan3 }}</td>
            <td>{{ d.FIELD17 }}</td>
            <td>{{ d.FIELD18 }}</td>
            <td>{{ d.umumiy_ball }}</td>
            <td>{{ d.Sana }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import sortedArray from "@/data/students";
import heading from "@/data/header";
import { reactive } from "vue";

export default {
  name: "App",
  setup() {
    const data = reactive(sortedArray);
    const head = reactive(heading);

    return {
      data,
      head,
    };
  },
};
</script>

<style scoped>
td {
  border: 1px solid lightgrey;
}
</style>