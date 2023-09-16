<template>
  <header class="header">
    <page-header
      title="Give me advice"
      text="Provide a number and get a piece of advice"
    ></page-header>
  </header>
  <main>
    <session>
      <page-form :quotes="quotes"> </page-form>
    </session>
    <session>
      <div>
        <h1>My name is Mohammed Dabour and welcome to my website</h1>
      </div>
    </session>
  </main>
</template>

<script>
import("./assets/css/style.css");
import PageHeader from "./components/PageHeader.vue";
import PageForm from "./components/PageForm.vue";
import advices from "../advices.json";

export default {
  name: "App",
  components: {
    PageHeader: PageHeader,
    PageForm: PageForm,
  },
  props: {
    quotes: Array,
  },
  provide() {
    return {
      newArray: this.advices,
      message: "hi this is your advice thanks for your time .",
    };
  },
  data() {
    return {
      advices,
    };
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

h1,
h2,
h3,
h4,
h6,
h5 {
  margin-bottom: 1rem;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
