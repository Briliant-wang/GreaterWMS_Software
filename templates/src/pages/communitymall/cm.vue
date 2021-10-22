<template>
  <div>
    <transition appear enter-active-class="animated fadeIn">
      <q-table
        class="my-sticky-header-column-table shadow-24"
        row-key="id"
        flat
        hide-bottom
      >
        <template v-slot:top >
          <q-card flat :style="{height:height}">
            <q-card-section horizontal :style="{width:width}" style="height:15%; background-color: #4C5875;font-size: 16px">
              <q-card-actions class="col-2" align="center">
                <div>
                  <p style="color: white;margin: 0;padding: 0">
                    {{$t('community_mall.cm.userlevel')}}
                  </p>
                </div>
              </q-card-actions>
              <q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>
                  <p style="color: white;margin: 0;padding: 0">
                    {{$t('community_mall.cm.receivingvolume')}}
                  </p>
                </div>
              </q-card-actions>
              <q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>
                  <p style="color: white;margin: 0;padding: 0">
                    {{$t('community_mall.cm.deliveringamount')}}
                  </p>
                </div>
              </q-card-actions>
              <q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>
                  <p style="color: white;margin: 0;padding: 0">
                    {{$t('community_mall.cm.users')}}
                  </p>
                </div>
              </q-card-actions>
              <q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>
                  <p style="color: white;margin: 0;padding: 0">
                    {{$t('community_mall.cm.useequipment')}}
                  </p>
                </div>
              </q-card-actions>
              <q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>
                  <p style="color: white;margin: 0;padding: 0">
                    {{$t('community_mall.cm.purchasemethod')}}
                  </p>
                </div>
              </q-card-actions>
            </q-card-section>
            <q-separator></q-separator>
            <!--            第二行-->
            <q-card-section horizontal style="height: 200px;font-size: 16px">
              <q-card-actions class="col-2" align="center" style="background-color: #DBDEE3">
                <div>{{$t('community_mall.cm.basicuser')}}</div>
              </q-card-actions>
              <q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>100</div>
              </q-card-actions>
              <q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>100</div>
              </q-card-actions>
              <q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>{{$t('community_mall.cm.unlimited')}}</div>
              </q-card-actions>
              <q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>{{$t('community_mall.cm.unlimited')}}</div>
              </q-card-actions>
              <q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>{{$t('community_mall.cm.noneedtobuy')}}</div>
              </q-card-actions>
            </q-card-section>
            <q-separator></q-separator>
            <!--            第三行-->
            <q-card-section horizontal style="height: 200px;font-size: 16px">
              <q-card-actions class="col-2" align="center" style="background-color: #DBDEE3">
                <div>{{$t('community_mall.cm.limitedusers')}}</div>
              </q-card-actions>
              <q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>1000</div>
              </q-card-actions><q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>1000</div>
              </q-card-actions><q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>{{$t('community_mall.cm.unlimited')}}</div>
              </q-card-actions><q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>{{$t('community_mall.cm.unlimited')}}</div>
              </q-card-actions>
              <q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <q-btn color="red" style="width: 140px;height: 48px;font-size: 16px" @click="open">
                  {{$t('community_mall.cm.buynow')}}
                </q-btn>
              </q-card-actions>
            </q-card-section>
            <q-separator></q-separator>
            <q-card-section horizontal style="height: 200px;font-size: 16px">
              <q-card-actions class="col-2" align="center" style="background-color: #DBDEE3">
                <div>{{$t('community_mall.cm.unlimitedusers')}}</div>
              </q-card-actions>
              <q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>{{$t('community_mall.cm.unlimited')}}</div>
              </q-card-actions><q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>{{$t('community_mall.cm.unlimited')}}</div>
              </q-card-actions><q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>{{$t('community_mall.cm.unlimited')}}</div>
              </q-card-actions><q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <div>{{$t('community_mall.cm.unlimited')}}</div>
              </q-card-actions>
              <q-separator vertical></q-separator>
              <q-card-actions class="col-2" align="center">
                <q-btn color="red" style="width: 140px;height: 48px;font-size: 16px" @click="open2">
                  {{$t('community_mall.cm.buynow')}}
                </q-btn>
              </q-card-actions>
            </q-card-section>
            <q-separator></q-separator>
          </q-card>
        </template>
      </q-table>
    </transition>
    <q-dialog v-model="payFrom1">
      <q-card style="min-width: 600px">
        <q-card-section style="width: 600px;height: 60px;background-color: #4C5875">
          <q-card-actions align="center">
            <p style="color: white;margin: 0;padding: 0;font-size: 20px">
              {{$t('community_mall.cm.buynow')}}
            </p>
          </q-card-actions>
        </q-card-section>
        <q-separator vertical></q-separator>
        <q-card-section style="height: 300px">
          <table>
            <tr>
              <td style="font-size: 18px;padding-top: 40px;padding-left: 40px" >
                {{ $t('community_mall.cm.purchasecontent') }}
              </td>
              <td style="font-size: 18px;padding-left: 10px;padding-top: 40px">
                {{ $t('community_mall.cm.lul') + $t('community_mall.cm.rasv') }}
              </td>
            </tr>
            <tr>
              <td style="font-size: 18px; padding-top: 40px; padding-left: 40px">
                {{ $t('community_mall.cm.paymentamount') }}
              </td>
              <td style="font-size: 18px; padding-left: 10px;padding-top: 40px; color: red">
                ￥1000
              </td>
            </tr>
            <tr>
              <td style="font-size: 18px;padding-top: 40px; padding-left: 40px">
                {{ $t('community_mall.cm.paymentmethods') }}
              </td>
              <td style="font-size: 18px; padding-left: 10px; padding-top: 40px">
                <q-btn style="background-color: #2255B4" @click="pay = true">
                  <img src="/statics/communitymall/paypal.png">
                </q-btn>
              </td>
            </tr>
          </table>
        </q-card-section>
      </q-card>
    </q-dialog>
    <q-dialog v-model="payFrom2">
      <q-card style="min-width: 600px">
        <q-card-section style="width: 600px;height: 60px;background-color: #4C5875">
          <q-card-actions align="center">
            <p style="color: white;margin: 0;padding: 0;font-size: 20px">
              {{$t('community_mall.cm.buynow')}}
            </p>
          </q-card-actions>
        </q-card-section>
        <q-separator vertical></q-separator>
        <q-card-section style="height: 300px">
          <table>
            <tr>
              <td style="font-size: 18px;padding-top: 40px;padding-left: 40px" >
                {{ $t('community_mall.cm.purchasecontent') }}
              </td>
              <td style="font-size: 18px;padding-left: 10px;padding-top: 40px">
                {{ $t('community_mall.cm.ulul') + $t('community_mall.cm.unlimiteds') }}
              </td>
            </tr>
            <tr>
              <td style="font-size: 18px; padding-top: 40px; padding-left: 40px">
                {{ $t('community_mall.cm.paymentamount') }}
              </td>
              <td style="font-size: 18px; padding-left: 10px;padding-top: 40px; color: red">
                ￥5000
              </td>
            </tr>
            <tr>
              <td style="font-size: 18px;padding-top: 40px; padding-left: 40px">
                {{ $t('community_mall.cm.paymentmethods') }}
              </td>
              <td style="font-size: 18px; padding-left: 10px; padding-top: 40px">
                <q-btn style="background-color: #2255B4" @click="open">
                  <img src="/statics/communitymall/paypal.png">
                </q-btn>
              </td>
            </tr>
          </table>
        </q-card-section>
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
      width: '100%',
      payFrom1: false,
      payFrom2: false,
      payFrom3: false
    }
  },
  methods: {
    open () {
      window.open('https://www.56yhz.com/')
    },
    open2 () {
      window.open('https://s.click.taobao.com/t?e=m%3D2%26s%3DMzMu%2FHKbwOlw4vFB6t2Z2ueEDrYVVa64Dne87AjQPk9yINtkUhsv0DyQlxakAd0P1CIF5vDaM198NL6699pKKym36gfsUjqbMPSskuId7r4qU4Ko02Q2Qo2X0110zJ5zgvUNyyJS1KL3%2BWMkG3VUs3iDi2ABgqxupKCoIsJ%2FFSbGkLzr5KaHAbfqK1v6Bu2O&union_lens=lensId%3AOPT%401634865570%400b5dc12f_9f1e_17ca594e23c_5492%4001')
    }
  },
  mounted () {
    var _this = this
    if (_this.$q.platform.is.electron) {
      _this.height = String(_this.$q.screen.height - 230) + 'px'
    } else {
      _this.height = _this.$q.screen.height - 230 + '' + 'px'
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
