<template>
  <Suspense>
    <template #default>
      <user />
    </template>
    <template #fallback>
      <p>Loading user</p>
    </template>
  </Suspense>  
</template>

<script>
import User from "./components/User.vue";
export default {
  name: "App",
  components: {
    User,
  },
};
</script>