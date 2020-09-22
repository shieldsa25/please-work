<template>
  <div class="modal">
    <div class="container">
      <div class="modal__title">Direction</div>
      <p>Get a direction with your favourite apps</p>
      <a href="#" class="btn gmaps">
        <img src="https://img.icons8.com/color/420/google-maps.png" /> Google
        Maps
      </a>
      <a href="#" class="btn waze">
        <img src="https://img.icons8.com/color/420/waze.png" /> Waze
      </a>
      <button class="mt-3 border-b border-teal font-semibold">Close</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal"
};
</script>

<style>
.modal {
  background-color: rgba(0, 0, 0, 0.7);
}
</style>
