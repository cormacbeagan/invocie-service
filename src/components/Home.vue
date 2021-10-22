<template>
  <div>
    <header>
      <h1>Mac's Self Service</h1>
    </header>
    <main>
      <button @click="this.invoice = !this.invoice">Invoice?</button>
      <div>
        <Form v-if="invoice" />
        <QuoteForm v-if="!invoice" />
      </div>
    </main>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Form from "./Form.vue";
import QuoteForm from "./QuoteForm.vue";

export default defineComponent({
  components: {
    Form,
    QuoteForm,
  },
  data() {
    return {
      invoice: Boolean,
    };
  },
  onLoad() {
    this.invoice = true;
  },
});
</script>

<style scoped>
footer {
  margin: 40px 0;
}
</style>
