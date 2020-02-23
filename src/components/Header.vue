<template>
  <div class="main">
    <h2>Quotes added</h2>
    <div class="bar">
      <div class="progress" :style="{width:number*10+'%'}">
        <p>{{number}}/10</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  props: ["number"]
};
</script>

<style scoped>
.main {
  margin-top: 5rem;
}

h2 {
  width: 200px;
  margin-bottom: 2rem;
  margin-left: 12.5%;
}

.bar {
  background-color: rgb(240, 240, 240);
  border-radius: 5px;
  width: 75%;
  margin: auto;

  box-shadow: -1px -1px rgb(200, 200, 200);
}

.progress {
  background-color: blue;
  border-radius: 5px;
}

p {
  color: white;
  text-align: center;
}
</style>
