<template>
  <div>
    <transition appear enter-active-class="animated fadeIn">
      <q-table
        class="my-sticky-header-column-table shadow-24"
        row-key="id"
        flat
        :style="{height:height}"
        hide-bottom
      >
        <template v-slot:top class="row">
          <q-card class="col-3">
            <q-card-section>
              <div class="text-h6" style="text-align: center">
                <p style="font-size: 28px;font-weight:Bold">
                  斑马DS4208SR扫描枪
                </p>
              </div>
              <div class="text-subtitle2" style="text-align: center">
                智能扫描 自动感应 抗摔性强 手感舒适
              </div>
              <div align="center" style="padding-top: 26px">
                <img src="/statics/communitymall/eq.png" style="height:141px;width: 208px">
              </div>
            </q-card-section>
            <q-card-actions align="center" style="background-color: #4C5875">
              <q-btn class="btn-fixed-width text-white" align="between" label="$1400" flat style="width: 100%;background-color: #4C5875" @click="details = true">
                {{ $t('community_mall.equipment.details') }}
              </q-btn>
            </q-card-actions>
          </q-card>
        </template>
      </q-table>
    </transition>
    <q-dialog v-model="details">
      <q-card style="min-width: 43%;min-height: 600px">
        <q-card-section horizontal>
          <q-card-section class="col-4">
           <q-card-section class="col-6">
             <q-img src="/statics/communitymall/eq1.png"/>
           </q-card-section>
            <q-separator vertical />
            <q-card-section class="col-6">
              <q-img src="/statics/communitymall/eq2.png" style="height: 50px;width: 50px"/>
              <q-img src="/statics/communitymall/eq3.png" style="height: 50px;width: 50px"/>
              <q-img src="/statics/communitymall/eq4.png" style="height: 50px;width: 50px"/>
              <q-img src="/statics/communitymall/eq5.png" style="height: 50px;width: 50px"/>
            </q-card-section>
          </q-card-section>
          <q-card-section class="col-8">
            <q-card-section>
              <div style="font-size: 18px;font-weight: bold">
                UROVO优博讯i6300A数据采集器聚水驿站旺店通中邮揽投物流快递超市壹米滴答众邮巴枪安卓PDA手持终端盘点机
              </div>
            </q-card-section>
            <hr>
            <q-card-section>
              <div>
                <span style="font-size: 14px">价格：</span>
                <span style="color: red;font-weight: bold;font-size: 24px">￥980</span>
                <span style="font-size: 14px;float: right;color: #999999">{{ $t('community_mall.equipment.salesvolume') }}2235</span>
              </div>
            </q-card-section>
            <hr>
            <q-card-actions class="my-card">
              <q-btn label="DS8178SR(DS6878SR升级版）二维无线USB接口" style="margin-left: 7px">
              </q-btn>
              <q-btn label="DS8108SR二维有线串口" style="margin-top: 14px">
              </q-btn>
              <q-btn label="DS8108SR二维有线USB接口" style="margin-top: 14px">
              </q-btn>
              <q-btn label="DS8178SR(DS6878SR升级版）二维无线串口" style="margin-top: 14px">
              </q-btn>
            </q-card-actions>
            <hr style="margin-top: 20px">
            <q-card-actions>
              <span>{{ $t('community_mall.equipment.quantity') }}</span>
                <q-btn-group style="width: 143px">
                  <q-btn flat @click="sub"><span style="font-size: 24px">-</span></q-btn>
                  <input type="text" style="color: red;font-size: 24px;font-weight: bold;width: 90px;border: 0px;text-align: center" placeholder="1" v-model="num">
                  <q-btn flat @click="add" align="right"><span style="font-size: 24px">+</span></q-btn>
                </q-btn-group>
            </q-card-actions>
            <hr style="margin-top: 20px">
          </q-card-section>
        </q-card-section>
        <q-card-actions align="center">
          <q-btn flat  align="center" color="white" style="background-color: red;height: 52px;width: 730px;font-size: 20px">
            {{ $t('community_mall.equipment.addtocart') }}
          </q-btn>
        </q-card-actions>
      </q-card>
    </q-dialog>
  </div>
</template>
<router-view />
<script>
export default {
  name: 'equipment',
  data () {
    return {
      height: '',
      height2: this.height / 4,
      width: '100%',
      details: false,
      num: 1
    }
  },
  methods: {
    add () {
      var _this = this
      _this.num++
    },
    sub () {
      var _this = this
      if (_this.num > 0) {
        _this.num--
      }
    }
  },
  mounted () {
    var _this = this
    if (_this.$q.platform.is.electron) {
      _this.height = String(_this.$q.screen.height - 150) + 'px'
    } else {
      _this.height = _this.$q.screen.height - 150 + '' + 'px'
    }
    if (_this.$q.platform.is.electron) {
      _this.width = String(_this.$q.screen.width - 250) + 'px'
    } else {
      _this.width = _this.$q.screen.width - 250 + '' + 'px'
    }
  },
  updated () {
  },
  destroyed () {
  }
}
</script>
