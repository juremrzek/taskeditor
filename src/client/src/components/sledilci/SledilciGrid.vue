<script setup>
import SledilecCard from "./SledilecCard.vue"
</script>

<template>
  <template v-for="sledilec in sledilci" :key="sledilec.id">
    <sledilec-card
      :sledilec="sledilec"
      :label="label"
      @sledi="(el) => $emit('sledi', el)"
      @odstrani="(el) => $emit('odstrani', el)"
    ></sledilec-card>
  </template>
</template>

<script>
export default {
  props: {
    sledilci: {
      type: Array,
      required: true,
    },
    label: {
      type: String,
      default: "Odstrani",
    },
  },
  emits: ["sledi", "odstrani"],
}
</script>
