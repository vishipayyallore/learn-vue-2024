<template>
  <div class="home">
    <div>
      <img class="robot" src="../assets/robot-home.png" aria-hidden="true" alt="Robot" />
    </div>
    <div class="get-started">
      <a href="">Get Started</a> building your first bot!
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.home
{
  text-align: center;
  color: #2c3e50;
}

.robot
{
  width: 300px;
  height: 300px;
}

.get-started
{
  font-size: 2em;
  padding-top: 20px;
}
</style>
