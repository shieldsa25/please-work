<template>
  <div class="column">
    <h1>{{ colname }}</h1>
    <div class="cards">
      <!-- <Card
        v-bind:card_title="cardData.card_title"
        v-bind:card_date="cardData.card_date"
      ></Card> -->
      <!-- <Card
        v-for="card in cardData"
        v-bind:key="card.card_title"
        v-bind:card_title="card.card_title"
        v-bind:card_date="card.card_date"
      ></Card> -->
      <!-- <draggable v-model="cardData" group="people" @start="drag=true" @end="drag=false">
        <div v-for="element in cardData" :key="element.id">{{element.name}}</div>
      </draggable> -->
      <draggable
        :list="cardData"
        :disabled="!enabled"
        class="list-group"
        ghost-class="ghost"
        :move="checkMove"
        @start="dragging = true"
        @end="dragging = false"
      >
        <div
          class="list-group-item"
          v-for="element in cardData"
          :key="element.card_title"
        >
          <!-- {{ element.card_title }} -->
          <Card
            v-bind:key="element.card_title"
            v-bind:card_title="element.card_title"
            v-bind:card_date="element.card_date"
          ></Card>
        </div>
      </draggable>
    </div>
    <rawDisplayer class="col-3" :value="cardData" title="List" />
  </div>
</template>

<script>
import Card from "@/components/Card.vue";
import draggable from 'vuedraggable';
import RawDisplayer from "@/components/RawDisplayer.vue";
let id = 1;
export default {
  name: "Column",
  components: {
    Card,
    draggable,
    RawDisplayer
  },
  props: {
    // msg: String
    colname: String
  },
  // dragging: false,
  display: "Simple",
  order: 0,
  data() {
    return {
      // cardData: {
      //   card_title: "just a string for now",
      //   card_date: 0,
      // },
      enabled: true,
      cardData: [
        { card_title: "just a string for now", card_date: 0, id: 0 },
        { card_title: "second card yay", card_date: 2, id: 1 },
        { card_title: "third card yay", card_date: 3, id: 2 }
      ],
      dragging: false
    };
  },

  computed: {
    draggingInfo() {
      return this.dragging ? "under drag" : "";
    }
  },
  methods: {
    add: function() {
      this.list.push({ name: "Juan " + id, id: id++ });
    },
    replace: function() {
      this.list = [{ name: "Edgard", id: id++ }];
    },
    checkMove: function(e) {
      window.console.log("Future index: " + e.draggedContext.futureIndex);
    }
  }

};
</script>

<style>
.column {
  border-style: solid;
  /* width: 50%; */
  /* height: 300px; */
}
</style>
