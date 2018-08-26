<template>
    <div class="row no-gutters">
        <div class="wrapper col-xs-12 col-sm-8 sm-offset-2 col-md-6 offset-md-3">
            <div class="header">
                test header
            </div>
            <div class="body ">
                <div class="row justify-content-between mb-3 mt-3">
                    <div class="col-6">
                        <span class="border border-dark rounded">1 + 1</span>
                    </div>
                    <div class="col-6">
                        <span class="border border-dark rounded">1 + 1</span>
                    </div>
                </div>
                <div class="row justify-content-between mb-3">
                    <div class="col-6">
                        <span class="border border-dark rounded">1 + 1</span>
                    </div>
                    <div class="col-6">
                        <span class="border border-dark rounded">1 + 1</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  data() {
    return {};
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
}

span:hover {
  background-color: #337ab7;
}
</style>

