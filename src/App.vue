<template>
  <div id="app">
    <VueTribute :options="options">
      <input placeholder="@...">
    </VueTribute>
    <div class="menu-container" ref="menuContainer">I'm a menu container</div>
  </div>
</template>

<script>
import VueTribute from "vue-tribute";
export default {
  name: "App",
  components: {
    VueTribute
  },
  data() {
    return {
      options: {
        trigger: "@",
        values: [
          { key: "Collin Henderson", value: "syropian" },
          { key: "Sarah Drasner", value: "sarah_edo" },
          { key: "Evan You", value: "youyuxi" },
          { key: "Adam Wathan", value: "adamwathan" }
        ],
        positionMenu: false,
        menuContainer: document.body
      }
    };
  },
  mounted() {
    this.options.menuContainer = this.$refs.menuContainer;
  }
};
</script>

<style lang="scss">
body {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
input {
  width: 400px;
  height: 44px;
  padding: 0 16px;
  font-size: 24px;
}

.menu-container {
  color: #fff;
  position: relative;
  margin: 100px auto 0;
  padding: 20px;
  background-color: #6638f0;
  width: 400px;
}

// Tribute styles
.tribute-container {
  position: absolute;
  top: 100%;
  left: 0;
  height: auto;
  max-height: 300px;
  max-width: 500px;
  overflow: auto;
  display: block;
  z-index: 999999;
  border-radius: 4px;
  box-shadow: 0 1px 4px rgba(#000, 0.13);
}
.tribute-container ul {
  margin: 0;
  margin-top: 2px;
  padding: 0;
  list-style: none;
  background: #fff;
  border-radius: 4px;
  border: 1px solid rgba(#000, 0.13);
  background-clip: padding-box;
  overflow: hidden;
}
.tribute-container li {
  color: #6638f0;
  padding: 5px 10px;
  cursor: pointer;
  font-size: 14px;
}
.tribute-container li.highlight,
.tribute-container li:hover {
  background: #6638f0;
  color: #fff;
}
.tribute-container li span {
  font-weight: bold;
}
.tribute-container li.no-match {
  cursor: default;
}
.tribute-container .menu-highlighted {
  font-weight: bold;
}
</style>
