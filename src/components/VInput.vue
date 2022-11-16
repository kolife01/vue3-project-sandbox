<script setup lang="ts">
import { computed } from "vue";

const props = defineProps({
  modelValue: String,
})
const emits = defineEmits(["update:modelValue"]);

const model = computed({
  get: () => props.modelValue,
  set: (value) => emits("update:modelValue", value),
});
</script>

<template>
  <input type="text" v-model="model" />
</template>
