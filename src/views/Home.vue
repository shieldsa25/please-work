<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png" /> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <!-- <Card msg="hey the first card" /> -->
    <!-- <Column msg="My Column" /> -->
    <!-- <div> -->
    <b-container class="bv-example-row">
      <b-row>
        <b-col v-for="columnObj in columnNames" v-bind:key="columnObj.num">
          <Column v-bind:colname="columnObj.name"></Column>
        </b-col>
      </b-row>
    </b-container>
    <!-- <Column
      v-for="columnObj in columnNames"
      v-bind:key="columnObj.name"
      v-bind:colname="columnObj.name"
    ></Column> -->
    <!-- </div> -->
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";
// import Card from "@/components/Card.vue";
import Column from "@/components/Column.vue";
// Worry about the modal once we get the basics going
// import ModalCard from "@/components/Modal";

export default {
  name: "Home",
  components: {
    // HelloWorld,
    // Card,
    Column
  },
  data() {
    return {
      columnNames: [
        { name: "Column1", num: 1 },
        // { name: "Column2", num: 2 }
      ]
    };
  }
};
</script>
