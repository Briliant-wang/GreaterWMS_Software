<template>
  <div>
    <transition appear enter-active-class="animated fadeIn">
      <q-table
        class="my-sticky-header-column-table shadow-24"
        row-key="id"
        :table-style="{ height: height }"
        flat
        :columns="columns"
        hide-bottom
      >
        <template v-slot:top>
          <q-card flat>
            <q-card-section horizontal :style="{width:width}" style="height:80px; background-color: #4C5875;font-size: 16px">
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
                  <q-btn color="red" style="width: 140px;height: 48px;font-size: 16px">
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
                  <q-btn color="red" style="width: 140px;height: 48px;font-size: 16px">
                    {{$t('community_mall.cm.buynow')}}
                  </q-btn>
              </q-card-actions>
            </q-card-section>
            <q-separator></q-separator>
          </q-card>
        </template>
      </q-table>
    </transition>
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
      width: '100%'
    }
  },
  mounted () {
    var _this = this
    if (_this.$q.platform.is.electron) {
      _this.height = String(_this.$q.screen.height - 200) + 'px'
    } else {
      _this.height = _this.$q.screen.height - 200 + '' + 'px'
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
