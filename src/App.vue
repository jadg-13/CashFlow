<template>
  <Suspense>
    <template #default>
      <HomePage/>
    </template>
    <template #fallback>
      <SplashScreen/>
    </template>
  </Suspense>
</template>

<script>
import SplashScreen from './components/SplashScreen.vue';
import { defineAsyncComponent } from "vue";

export default {
  components: {
    SplashScreen,
    HomePage: defineAsyncComponent(
      () =>
        new Promise((resolve) => {
          setTimeout(() => {
            resolve(import("./components/HomePage.vue"));
          }, 1300);
        }))

  },
};
</script>

<style>
html,
body,
.app {
  min-height: 100vh;
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}

* {
  --brand-green: #04b500;
  --brand-blue: #0689b0;
}
</style>
