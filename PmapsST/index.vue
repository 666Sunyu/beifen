<template>
  <div class="PMAPSST">
    <div class="bj">
      <div class="bj1">
        <div class="select">
          <div class="selectTop">
            <div class="option">
              <div class="border"  :class="{'avtiveB':active==='1'}">
                <span>collect</span>
              </div>
              <div class="arrows">
                <img src="./img/arrows1.png" alt />
              </div>
            </div>
            <div class="option">
              <div class="border"  :class="{'avtiveB':active==='2'}">
                <span>flowoption</span>
              </div>
              <div class="arrows">
                <img src="./img/arrows1.png" alt />
              </div>
            </div>
            <div class="option">
              <div class="border"  :class="{'avtiveB':active==='3'}">
                <span>边界条件生成</span>
              </div>
              <div class="arrows">
                <img src="./img/arrows1.png" alt />
              </div>
            </div>
            <div class="option">
              <div class="border" :class="{'avtiveB':active==='4'}">
                <span>DFB</span>
              </div>
            </div>
          </div>
          <div class="selectBottom">
            <div class="option">
              <div class="border" :class="{'avtiveB':active==='5'}">
                <span>WRF4RADAR</span>
              </div>
              <div class="arrows1">
                <img src="./img/arrows2.png" alt />
              </div>
            </div>
            <div class="option">
              <div class="border" :class="{'avtiveB':active==='6'}">
                <span>WRF</span>
              </div>
              <div class="arrows1">
                <img src="./img/arrows2.png" alt />
              </div>
            </div>
            <div class="option">
              <div class="border" :class="{'avtiveB':active==='7'}">
                <span>VAR_RADAR</span>
              </div>
              <div class="arrows1">
                <img src="./img/arrows2.png" alt />
              </div>
            </div>
            <div class="option">
              <div class="border" :class="{'avtiveB':active==='8'}">
                <span>VAR_GTS</span>
              </div>
              <div class="arrows2">
                <img src="./img/arrows3.png" alt />
              </div>
            </div>
          </div>
        </div>
        <div class="show">
          <component is="BianJie"></component>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BianJie from '@/views/PmapsST/components/BianJie.vue'
export default {
  data () {
    return {
      active: '1',
      componentObj: [
        { num: '1', com: 'BianJie' },
        { num: '2', com: 'BianJie' },
        { num: '3', com: 'BianJie' },
        { num: '4', com: 'BianJie' },
        { num: '8', com: 'BianJie' },
        { num: '7', com: 'BianJie' },
        { num: '6', com: 'BianJie' },
        { num: '5', com: 'BianJie' }
      ]
    }
  },
  components: {
    BianJie
  },
  methods: {
    activeNum () {
      var i = 0
      const timer = setInterval(() => {
        if (i <= 7) {
          this.active = this.componentObj[i].num
          i++
        } else {
          i = 0
          this.active = this.componentObj[i].num
          i++
        }
      }, 1000)
    }
  },
  created () {
    this.activeNum()
  }
}
</script>

<style lang="less" scoped>
@keyframes arrowsRight {
  0% {
    transform: translateX(-5%);
  }
  100% {
    transform: translateX(5%);
  }
}
@keyframes arrowsLeft {
  0% {
    transform: translateX(5%);
  }
  100% {
    transform: translateX(-5%);
  }
}
@keyframes arrowsBottom {
  0% {
    transform: translateY(-5%);
  }
  100% {
    transform: translateY(5%);
  }
}
.PMAPSST {
  box-sizing: border-box;
  width: 100%;
  height: 100%;
  background: url("./img/stbeijing.png") no-repeat;
  background-size: 100% 100%;
  .bj {
    background: url("./img/stBorder.png") no-repeat;
    background-size: 100% 100%;
    height: 100%;
    width: 100%;
    .bj1 {
        height: 100%;
      display: flex;
      .select {
        margin-top: 100px;
        flex: 1;
        padding-left: 85px;
        .selectTop {
          display: flex;
        }
        .selectBottom {
          display: flex;
          margin-top: 150px;
          position: relative;
        }
        .option {
          width: 450px;
          height: 297px;
          display: flex;
          .border {
            width: 314px;
            height: 297px;
            line-height: 297px;
            background: url("./img/组394.png") no-repeat;
            text-align: center;
            span {
              font-size: 43px;
              font-weight: 700;
              color: #00f5ff;
            }
          }
          .avtiveB {
            background: url("./img/active.png") no-repeat;
          }
          .arrows {
            width: 136px;
            text-align: center;
            line-height: 297px;
            img {
              vertical-align: middle;
              animation: arrowsRight 2s infinite linear;
            }
          }
          .arrows1 {
            width: 136px;
            text-align: center;
            line-height: 297px;
            img {
              vertical-align: middle;
              animation: arrowsLeft 2s infinite linear;
            }
          }
          .arrows2 {
            position: absolute;
            right: 320px;
            top: -120px;
            img {
              vertical-align: middle;
              animation: arrowsBottom 2s infinite linear;
            }
          }
        }
      }
      .show {
        flex: 1;
        margin-top: 100px;

        // background-color: #fff;
      }
    }
  }
}
</style>
