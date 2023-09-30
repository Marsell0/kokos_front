<script setup>
import { reactive } from "vue";
import TableLite from "vue3-table-lite";

const table = reactive({
  isLoading: false,
  columns: [
    {
      label: "ФИО",
      field: "fio",
      width: "15%",
      sortable: true,
      isKey: true,
    },
    {
      label: "Вид спорта",
      field: "sport",
      width: "10%",
      sortable: true,
    },
    {
      label: "Вклад",
      field: "money",
      width: "5%",
      sortable: true,
    },
    {
      label: "Место",
      field: "place",
      width: "5%",
      sortable: true,
    },
  ],
  rows: [],
  totalRecordCount: 0,
  sortable: {
    order: "id",
    sort: "asc",
  },
});
</script>

<template>
  <table-lite
    :is-loading="table.isLoading"
    :columns="table.columns"
    :rows="table.rows"
    :total="table.totalRecordCount"
    :sortable="table.sortable"
    :messages="table.messages"
    @do-search="doSearch"
    @is-finished="table.isLoading = false"
  />
</template>

<style scoped></style>
