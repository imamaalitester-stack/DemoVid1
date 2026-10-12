<script setup>
import { ref } from "vue";

const total = ref(4200);

async function pay() {
  await fetch("/api/checkout", {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({ amount: total.value }),
  });
}
</script>

<template>
  <button @click="pay">Pay {{ total }}</button>
</template>
