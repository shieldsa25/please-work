<template>
  <div class="card">
    <!-- <h1>{{ msg }}</h1> -->
    <!-- <h3>Card Title: {{ cardData.card_title }}</h3>
    <h3>Date Created: {{ cardData.card_date }}</h3> -->
    <h3>Card Title: {{ card_title }}</h3>
    <h3>Date Created: {{ card_date }}</h3>
    <div class = buttons>
    <button v-on:click="deleteCard">Delete?</button>
    <!-- <div class = buttons>
      <button v-on:click="deleteCard">Delete?</button>
    </div> -->
    <button v-on:click="closeCard">Close</button>
  </div>
  </div>
  <!-- <ModalCard></ModalCard> -->
</template>

<script>
export default {
  name: "Card",
  // components: {
  //   ModalCard
  // },
  props: {
    // msg: String,
    card_title: String,
    card_date: Number
  },
  // data() {
  //   // card_data: {
  //   return {
  //     cardData: {
  //       card_title: "just a string for now",
  //       card_date: 0,
  //     },
  //   // }
  //   }
  // },

  methods: {
    deleteCard: function() {
      alert("Hi");
    },
    closeCard: function() {
      console.log("just a placeholder for later things");
    },
    startDrag: (evt, item) => {
      console.log("in startDrag")
      evt.dataTransfer.dropEffect = 'move'
      evt.dataTransfer.effectAllowed = 'move'
      evt.dataTransfer.setData('itemID', item.id)
    },
    onDrop (evt, list) {
      console.log("in onDrop")
      const itemID = evt.dataTransfer.getData('itemID')
      const item = this.items.find(item => item.id == itemID)
      item.list = list
}
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* .buttons {
    position: absolute;
    left: 0;
  } */
.card {
  border-style: solid;
  /* width: 50%; */
  /* height: 300px; */
}
</style>
