<template>
  <div id="app">
    <ReqList/>
  </div>
</template>

<script>
import ReqList from './components/ReqList.vue';

export default {
  components: {
    ReqList
  }
};
</script>

<style>
#app{
  background-color: rgb(188, 220, 186);
  border-radius: 25px;
  padding: 10px;
}
</style>