<template>
  <div id="app">
    <div class="container">
        <div class="row justify-content-center align-items-center">
          <h1>Welcome to Simple Math done!</h1>
        </div>
        <hr>
        <transition mode="out-in" :enter-active-class="selectedComponent != 'math-solver' ? 'animated tada' : 'animated fadeIn'" leave-active-class="animated fadeOut" appear appear-active-class="animated bounceIn">
          <component :is="selectedComponent"
          :maxRows=2
          :maxColumns=2
          :maxRandVal=100
          @correctSelected="showSuccessComponent"
          @startNewGame="startNewGame"></component>
        </transition>
      </div>
  </div>
</template>

<script>
import MathSolver from "./components/MathSolver";
import Winner from "./components/Winner";
export default {
  data() {
    return {
      selectedComponent: "math-solver"
    };
  },
  methods: {
    showSuccessComponent() {
      this.selectedComponent = "winner";
    },
    startNewGame() {
      this.selectedComponent = "math-solver";
    }
  },
  components: {
    MathSolver,
    Winner
  }
};
</script>

