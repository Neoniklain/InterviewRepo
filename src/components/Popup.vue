<script>
export default {
  name: "Popup",
  props: {
    text: {
      type: String,
      default: "",
    },
  },
};
</script>

<template>
  <div v-if="text" class="popup">
    {{ text }}
  </div>
</template>


<style lang="scss">
.popup {
  position: absolute;
  right: 24px;
  bottom: 24px;
  font-size: 18px;
  border: 1px solid black;
  border-radius: 10px;
  box-shadow: 5px 8px 12px 0px #0000007d;
  padding: 16px;
}
</style>