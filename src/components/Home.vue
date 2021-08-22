<template>
  <div>
    <header>
      <h1>Mac's Invoice Service</h1>
    </header>
    <main>
      <Form />
    </main>
    <footer>
      <a class="button" href="./assets/dummyData.json" download>Dummy Data</a>
    </footer>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Form from "./Form.vue";

export default defineComponent({
  components: {
    Form,
  },
});
</script>

<style scoped>
footer {
  margin: 40px 0;
}
</style>
