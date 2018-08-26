<template>
    <div class="row no-gutters">
        <div class="wrapper col-xs-12 col-sm-8 sm-offset-2 col-md-6 offset-md-3">
            <div class="header mb-4">
                {{selected}}
            </div>
            <div class="body">
                <div class="row justify-content-between mb-4" v-for="(row, index) in solutions" :key="index">
                    <div class="col-6" v-for="solution in row" :key="solution.id">
                        <span @click="isCorrect(solution)" class="border border-dark rounded">{{solution.str}}</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import uniqueId from "lodash.uniqueid";
export default {
  props: ["maxRows", "maxColumns", "maxRandVal"],
  data() {
    return {
      mathProblem: {},
      solutions: this.generateSolutions(),
      selected: 0,
      index: 0
    };
  },
  created() {
    this.selected = this.selectMathSolution();
  },
  methods: {
    isCorrect(solution) {
      if (solution.val != this.selected) {
        alert("Incorrect decision");
      } else {
        this.$emit("correctSelected");
      }
    },
    generateSolutions() {
      let solutions = [];
      for (let row = 0; row < this.maxRows; row++) {
        let columns = [];
        for (let column = 0; column < this.maxColumns; column++) {
          const a = Math.floor(Math.random() * this.maxRandVal);
          const b = Math.floor(Math.random() * this.maxRandVal);
          columns.push({ val: a + b, str: `${a}+${b}`, id: uniqueId() });
        }
        solutions.push(columns);
      }
      return solutions;
    },
    selectMathSolution() {
      const x = Math.round(Math.random() * (this.maxRows - 1));
      const y = Math.round(Math.random() * (this.maxColumns - 1));
      return this.solutions[x][y].val;
    }
  }
};
</script>

<style scoped>
.header {
  border-bottom: 1px solid black;
  background-color: #e0e0e0;
  padding: 10px;
  font-weight: bold;
}

.wrapper {
  border: 1px solid black;
  text-align: center;
}

span {
  background-color: #1d98c7;
  padding: 5px;
  cursor: pointer;
  color: white;
}

span:hover {
  background-color: #337ab7;
}
</style>

