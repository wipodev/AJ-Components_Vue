<template>
  <div class="header">
    <h2>Custom Menu</h2>
    <input id="btn-menu" type="checkbox" />
    <label for="btn-menu">
      <img src="http://img.icons8.com/ios/1600/squared-menu.png" alt="menu" />
    </label>
    <nav class="menu">
      <transition-group name="desliza">
        <a v-for="l of lista" :id="l" :key="l" href="#">Menu-{{ l }}</a>
      </transition-group>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lista: ["uno", "dos", "tres"],
    };
  },
};
</script>

<style scoped>
.header {
  width: 100%;
  height: 70px;
  background: rgba(0, 0, 0, 0.5);
  color: white;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 100;
  text-align: center;
}

#btn-menu {
  display: none;
}

.header label {
  font-size: 60px;
  cursor: pointer;
  position: absolute;
  top: 0;
  right: 0;
  width: 70px;
  height: 70px;
}

label img {
  width: 100%;
}

.menu {
  position: absolute;
  top: 70px;
  left: 0;
  width: 100%;
}

.menu a {
  display: block;
  color: white;
  height: 50px;
  background: rgba(0, 0, 0, 0.4);
  text-decoration: none;
  padding: 15px;
  text-align: center;
  border-top: 1px solid #fff;
  margin-top: -100%;
}

.menu a:hover {
  background: rgba(0, 0, 0, 0.6);
}

.menu #uno {
  transition: all 0.2s;
}
.menu #dos {
  transition: all 0.4s;
}
.menu #tres {
  transition: all 0.6s;
}
.menu #cuatro {
  transition: all 0.8s;
}

#btn-menu:checked ~ .menu a {
  margin-top: 0;
}
</style>
