<template>
    <div>
      <h3>{{ title }}</h3>
      <pre>{{ valueString }}</pre>
    </div>
</template>

<script>
// This code is from the following link
// https://github.com/SortableJS/Vue.Draggable/blob/master/example/components/infra/raw-displayer.vue
  const props = {
    name: "raw-displayer",
    title: {
      required: true,
      type: String
    },
    value: {
      required: true
    }
  };
  export default {
    props,
    computed: {
      valueString() {
        return JSON.stringify(this.value, null, 2);
      }
    }
  };
</script>

<style scoped>
  pre {
    text-align: start;
  }
  </style>