<template>
  <div>
    <p>Dimas Ganteng</p>
    <h2>{{ nama }}</h2>
    <h2>{{ umur }}</h2>
  </div>
</template>

<script>
export default {
  name:'MyComponent',
  props: ["nama", "umur"],
};
</script>
