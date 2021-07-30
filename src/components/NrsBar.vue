<template xmlns:v-touch="http://www.w3.org/1999/xhtml">
  <div class="nrs-bar">
    <div class="bar">
      <div class="inner">
      </div>
    </div>
    <div class="text text-0">0</div>
    <div class="text text-3">3</div>
    <div class="text text-7">7</div>
    <div class="nrs-val" :style="val_pos">
      <div class="val" :style="val_bg"> {{ value }}分
        <i :style="pos_border"></i>
        <div :style="val_bg" class="point"></div>
      </div>
    </div>
    <div class="info-left">无营养风险</div>
    <div class="info-right">有营养风险</div>
  </div>
</template>


<script>
export default {
  props: ["value"],
  computed: {
    val_pos () {
      var val = parseInt(this.value) || 0;
      var percent = (val / 7) * 100;
      return {
        left: percent + '%'
      }
    },
    val_bg () {
      var val = parseInt(this.value) || 0;
      if (val >= 3) {
        return { background: '#ed564e' }
      } else {
        return { background: '#68ba65' }
      }
    },
    pos_border () {
      var val = parseInt(this.value) || 0;
      if (val >= 3) {
        return { "border-top": "10px solid #ed564e" }
      } else {
        return { "border-top": "10px solid #68ba65" }
      }
    }
  },
}
</script>


<style >
.nrs-bar {
  position: relative;
  padding-top: 50px;
}
.nrs-bar .bar {
  height: 6px;
  overflow: hidden;
  background: #68ba65;
  position: relative;
}
.nrs-bar .bar .inner {
  height: 6px;
  overflow: hidden;
  background: #ed564e;
  border-left: 2px solid #fff;
  right: 0;
  top: 0;
  width: 57%;
  position: absolute;
}
.nrs-bar .text {
  color: #a8a8a8;
  font-size: 10px;
  top: 35px;
}
.nrs-bar .text-0 {
  position: absolute;
  left: 0;
}
.nrs-bar .text-3 {
  position: absolute;
  right: 57%;
}
.nrs-bar .text-7 {
  position: absolute;
  right: 0;
}
.nrs-val {
  position: absolute;
  top: 8px;
}
.nrs-val .val {
  padding: 5px 12px;
  width: 30px;
  margin-left: -23px;
  height: 18px;
  border-radius: 12px;
  color: #fff;
  margin-bottom: 20px;
  font-size: 14px;
  text-align: center;
  line-height: 18px;
  position: relative;
}
.nrs-val .val i {
  width: 0;
  height: 0;
  border: 8px solid transparent;
  position: absolute;
  left: 50%;
  bottom: -15px;
  margin-left: -8px;
}
.nrs-val .point {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  position: absolute;
  left: 50%;
  margin-left: -5px;
  bottom: -23px;
  border: 2px solid #fff;
}

.nrs-bar .info-left {
  font-size: 12px;
  font-weight: bold;
  padding: 5px;
}

.nrs-bar .info-right {
  font-size: 12px;
  position: absolute;
  right: 0;
  bottom: 0;
  font-weight: bold;
  padding: 5px;
}
</style>