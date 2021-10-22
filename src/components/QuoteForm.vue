<template>
  <div class="form-container">
    <form @submit.prevent="handleSubmit($event)">
      <label class="button"
        >Upload a JSON file quote
        <input type="file" @change="handleInput" style="display:none;" />
      </label>
      <button type="submit" class="button" :disabled="!jsonData">
        Download PDF
      </button>
    </form>
    <button v-if="jsonData" class="button" @click="jsonData = null">
      Clear Data
    </button>
    <pre v-if="jsonData">{{ jsonData }}</pre>
  </div>
  <footer>
    <a class="button" href="./assets/dummyQuoteData.json" download
      >Dummy Data</a
    >
  </footer>
</template>

<script>
import { defineComponent } from "vue";
import createPDFQuote from "macs-pdf-quote";

export default defineComponent({
  components: {},
  data() {
    return {
      jsonData: null,
    };
  },
  methods: {
    async handleSubmit() {
      console.log(this.jsonData);
      createPDFQuote(this.jsonData);
    },
    async fileToJSON(file) {
      return new Promise((resolve, reject) => {
        const fileReader = new FileReader();
        fileReader.onload = (event) => resolve(JSON.parse(event.target.result));
        fileReader.onerror = (error) => reject(error);
        fileReader.readAsText(file);
      });
    },
    async handleInput(e) {
      const data = await this.fileToJSON(e.target.files[0]);
      this.jsonData = data;
    },
  },
});
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

pre {
  margin: 20px auto;
  text-align: left;
  max-width: 516px;
  background: rgb(48, 70, 95);
  color: rgb(233, 181, 86);
  padding: 20px;
  border-radius: 10px;
  font-size: 16px;
}
</style>
