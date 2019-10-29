<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="main">
      <div class="keyword">
        <input type="text" />
      </div>
      <ul>
        <li></li>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  created() {
    console.log("xx");
    axios
      .get("/api/airport/search", {
        params: {
          keyword: "guangzhou"
        }
      })
      .then(res => {
        console.log(res);
      })
      .catch(error => {
        console.log(error);
      });
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
