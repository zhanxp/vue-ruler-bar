<template xmlns:v-touch="http://www.w3.org/1999/xhtml">
  <div class="nut-bar">
    <div class="bar">
      <div class="inner2">
      </div>
      <div class="inner1">
      </div>
    </div>
    <div class="text text-44">44</div>
    <div class="text text-66">66</div>
    <div class="nut-val" :style="val_pos">
      <div class="val" :style="val_bg"> {{ value }}分
        <i :style="pos_border"></i>
        <div :style="val_bg" class="point"></div>
      </div>
    </div>
    <div class="info-left">需要营养干预</div>
    <div class="info-center">有营养不良风险</div>
    <div class="info-right">正常</div>
  </div>
</template>


<script>
export default {
  props: ["value"],
  computed: {
    val_pos () {
      var val = parseInt(this.value) || 0;
      var percent = (val / 110) * 100;
      return {
        left: percent + '%'
      }
    },
    val_bg () {
      var val = parseInt(this.value) || 0;
      if (val >= 66) {
        return { background: '#6abb67' }
      } else if (val > 43) {
        return { background: '#f09352' }
      } else {
        return { background: '#ed564e' }
      }
    },
    pos_border () {
      var val = parseInt(this.value) || 0;
      if (val >= 66) {
        return { "border-top": "10px solid #6abb67" }
      } else if (val > 43) {
        return { "border-top": "10px solid #f09352" }
      } else {
        return { "border-top": "10px solid #ed564e" }
      }
    }
  },
}
</script>


<style >
.nut-bar {
  position: relative;
  padding-top: 50px;
}
.nut-bar .bar {
  height: 6px;
  overflow: hidden;
  background: #ed564e;
  position: relative;
}
.nut-bar .bar .inner1 {
  height: 6px;
  overflow: hidden;
  background: #f09352;
  border-left: 2px solid #fff;
  border-right: 2px solid #fff;
  left: 40%;
  right: 40%;
  top: 0;
  position: absolute;
}
.nut-bar .bar .inner2 {
  height: 6px;
  overflow: hidden;
  background: #6abb67;
  left: 60%;
  right: 0;
  top: 0;
  position: absolute;
}
.nut-bar .text {
  color: #a8a8a8;
  font-size: 10px;
  top: 35px;
}

.nut-bar .text-44 {
  position: absolute;
  left: 40%;
}
.nut-bar .text-66 {
  position: absolute;
  left: 60%;
}
.nut-val {
  position: absolute;
  top: 8px;
}
.nut-val .val {
  padding: 5px 12px;
  width: 30px;
  margin-left: -23px;
  height: 18px;
  border-radius: 12px;
  color: #fff;
  margin-bottom: 20px;
  font-size: 12px;
  text-align: center;
  line-height: 18px;
  position: relative;
}
.nut-val .val i {
  width: 0;
  height: 0;
  border: 8px solid transparent;
  position: absolute;
  left: 50%;
  bottom: -15px;
  margin-left: -8px;
}
.nut-val .point {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  position: absolute;
  left: 50%;
  margin-left: -5px;
  bottom: -23px;
  border: 2px solid #fff;
}

.nut-bar .info-left {
  font-size: 14px;
  font-weight: bold;
  padding: 5px;
  position: absolute;
  left: 0;
  bottom: 0;
}

.nut-bar .info-center {
  font-size: 12px;
  font-weight: bold;
  padding: 5px;
  text-align: center;
}

.nut-bar .info-right {
  font-size: 12px;
  position: absolute;
  right: 0;
  bottom: 0;
  font-weight: bold;
  padding: 5px;
}
</style>