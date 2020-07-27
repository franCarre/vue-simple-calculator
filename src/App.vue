<template>
  <div id="app">
    <a @click="themeSwitch" id="switch"><i class="fas fa-moon"></i></a>
    <Calculator />
  </div>
</template>

<script>
import Calculator from './components/Calculator.vue'
export default {
  name: 'App',
  components: {
    Calculator
  },
  methods: {
    darkTheme() {
      let darkTheme = document.getElementById("light-theme");
      darkTheme.setAttribute("href", "/css/dark.css");
      darkTheme.setAttribute("id", "dark-theme");
      document.querySelector('#switch').innerHTML = '<i class="fas fa-sun"></i>';
    },
    lightTheme() {
      let lightTheme = document.getElementById("dark-theme");
      lightTheme.setAttribute("href", "/css/light.css");
      lightTheme.setAttribute("id", "light-theme");
      document.querySelector('#switch').innerHTML = '<i class="fas fa-moon"></i>';
    },
    themeSwitch() {
      let darkTheme = document.querySelector("#dark-theme");
      if (!darkTheme) {
        this.darkTheme()
      } else {
        this.lightTheme()
      }
    }
  }
}
</script>