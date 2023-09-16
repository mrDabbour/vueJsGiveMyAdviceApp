<template>
  <!-- {{ newArray }} -->
  <form class="form">
    <fieldset class="form-fieldset">
      <legend class="form-legend">Choose a number</legend>
      <label class="form-label">Luck Number</label>
      <input class="form-input" type="number" v-model="userNumber" />
    </fieldset>

    <fieldset class="form-fieldset">
      <legend class="form-legend">Text Color</legend>
      <label class="form-label">Color</label>
      <input class="form-input" type="color" v-model="userColor" />
    </fieldset>
    <div>
      {{ getAdvice }}
      {{ userColor }}
    </div>
    <form-result :color="userColor" :advice="getAdvice"></form-result>
  </form>
</template>
<script>
import FormResult from "./FormResult.vue";
export default {
  name: "PageForm",
  data() {
    return {
      userNumber: 2,
      userColor: "#000000",
    };
  },
  components: {
    FormResult,
  },
  inject: ["newArray", "message"],
  computed: {
    getAdvice() {
      const advice = this.newArray.find((q, i) => i === this.userNumber);
      console.log(advice);
      if (!advice) return "unlucky enough , no advice for you";
      return advice.quoteText;
    },
  },
};
</script>

<style scoped>
/* Add your CSS styles for the form here */

.form {
  margin: 5rem auto;
  max-width: 70%;
}

.form-fieldset {
  margin: 2rem 0;
  padding: 2rem;
  border-radius: 10px;
  background: linear-gradient(80deg, #e5e5e5, lightblue);
}

.form-legend {
  display: block;
  padding: 1rem;
  font-size: 1.5rem;
  font-weight: bold;
  background: linear-gradient(80deg, yellow, lightgreen);
  border-radius: 15px;
}

.form-label {
  display: block;
  padding: 1rem;
  font-size: 1.5rem;
  border-radius: 15px;
}
.form-input {
  outline: none;
  border: none;
  font-size: 2rem;
  color: tomato;
  text-align: center;
  max-width: 30%;
}
</style>
