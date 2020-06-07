<template>
  <div>
    <input @input="onInput" />
    <button class="btn btn-primary" @click="onClick">Click</button>
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  methods: {
    onClick: function() {
      this.$emit("termChange", this.message);
    },
    onInput(event) {
      this.message = event.target.value;
    }
  },
  data() {
    return {
      message: ""
    };
  }
};
</script>


<style scoped>
input {
  width: 75%;
  height: 40px;
}
button {
  width: 20%;
  margin-left: 10px;
  height: 40px;
}
div {
  display: flex;
  justify-content: space-around;
  margin: 30px;
}
</style>