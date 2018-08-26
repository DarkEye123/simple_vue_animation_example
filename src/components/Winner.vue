<template>
    <div class="row no-gutters">
        <div class="wrapper col-xs-12 col-sm-8 sm-offset-2 col-md-6 offset-md-3">
            <div class="header mb-4">
                <H1>Congratulation!!!</H1>
            </div>
            <div class="body">
                <!-- <span>You won the game, do you want to continue?</span> -->
                <p>You won the game, do you want to continue?</p>
                <div class="btn btn-lg btn-primary mb-4" @click="$emit('startNewGame')">start a new game</div>
            </div>
        </div>
    </div>
</template>

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
</style>
