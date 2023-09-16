<template>
  
      <h1 class="header-heading">{{title}}</h1>
    <p class="header-text">{{text}}</p>
</template>
<script>
export default {
  name: 'PageHeader',
  props:['title','text']
};
</script>
<style>

p {
  color: #fff;
}
header {
  background: #333;
  color: #fff;
  padding: 1rem;
}
</style>
