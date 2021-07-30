<template>
  <div>
    <h1>仅限于移动端</h1>
    体重
    <DLRuler :value="50" :min="30" unit="cm" :max="300" :change="changeWeight"></DLRuler>
    身高
    <DLRuler :value="60" :min="10" :max="100"></DLRuler>
    <!-- 测试
    <DLRuler :value="35" :min="10" :max="120"></DLRuler> -->
    Nrs评分<br />
    <NrsBar :value="3"></NrsBar><br />
    Nut评分<br />
    <div style="padding-left:25px;padding-right:30px;">
      <NutBar :value="40"></NutBar>
    </div>
    <br />
  </div>

</template>
<script>
import DLRuler from './components/DLRuler.vue';
import NrsBar from './components/NrsBar.vue';
import NutBar from './components/NutBar.vue';

export default {
  components: {
    DLRuler,
    NrsBar,
    NutBar
  },
  data: function () {
    return {}
  },
  computed: {},
  created: function () {

  },
  methods: {
    changeWeight (val) {
      console.log(val);
    }
  }
}
</script>
<style>
</style>
