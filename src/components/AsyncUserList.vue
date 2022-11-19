<script setup lang="ts">
import { ref } from "vue";

interface User {
  id: number;
  username: string;
}

const result = await fetch("https://jsonplaceholder.typicode.com/users");
const json = await result.json();

const users = ref<User[]>(json);
</script>

<template>
  <ul>
    <p>AsyncUserList</p>
    <li v-for="user in users" :key="user.id">
      {{ user.username }}
    </li>
  </ul>
</template>