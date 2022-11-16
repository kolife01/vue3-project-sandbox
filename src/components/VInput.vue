<script setup lang="ts">
import { computed } from "vue";

const props = defineProps({
  modelValue: String,
})
const emits = defineEmits(["update:model"]);

// template側が object になる
const model = computed(() => ({
  get: () => props.modelValue,
  set: (value) => emits("update:model", value),
}));
</script>

<template>
  <input type="text" v-model="model" />
</template>
