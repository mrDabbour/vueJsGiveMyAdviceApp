<template>
  {{ message }}
  <div class="result-box">
    <p class="result-title">Here is your advice :</p>
    <p class="result-text" :style="{ color: color }">{{ advice }}</p>
  </div>
</template>

<script>
export default {
  name: "FormResult",
  props: ["advice", "color" ],
  inject: ["newArray"],
};
</script>
<style scoped>
.result-box {
  margin: 2rem;
  border-radius: 15px;
  padding: 2rem;
  background: linear-gradient(80deg, #e5e5e5, lightblue);
}

.result-title {
  background: linear-gradient(80deg, yellow, lightgreen);
  padding: 2rem;
  color: black;
  font-weight: bold;
  font-size: 2rem;
}

.result-text {
  font-size: 3rem;
  color: black;
  line-height: 3rem;
}
</style>
