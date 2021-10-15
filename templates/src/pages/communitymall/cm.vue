<template>
  <div>
    <transition appear enter-active-class="animated fadeIn">
      <q-table
        class="my-sticky-header-table shadow-24"
        :data="data"
        row-key="name"
        :separator="separator"
        :loading="loading"
        :filter="filter"
        :columns="columns"
        hide-bottom
        :pagination.sync="pagination"
        no-data-label="No data"
        no-results-label="No data you want"
        :table-style="{ height: height }"
        flat
        bordered
      >
<!--        <template v-slot:body="props">-->
<!--          <q-tr props="props">-->
<!--            <q-td key="" props="props">-->
<!--              {{props.row.userlevel}}-->
<!--            </q-td>-->
<!--            <q-td key="" props="props">-->
<!--              {{ props.row.receivingvolume }}-->
<!--            </q-td>-->
<!--            <q-td key="" props="props">-->
<!--              {{ props.row.deliveringamount }}-->
<!--            </q-td>-->
<!--            <q-td key="" props="props">-->
<!--              {{ props.row.users }}-->
<!--            </q-td>-->
<!--            <q-td key="" props="props">-->
<!--              {{ props.row.useequipment }}-->
<!--            </q-td>-->
<!--            <q-td key="" props="props">-->
<!--              {{ props.row.purchasemethod }}-->
<!--            </q-td>-->
<!--          </q-tr>-->
<!--        </template>-->
      </q-table>
    </transition>
  </div>
</template>
<router-view />

<script>
import { getauth } from 'boot/axios_request'
import { LocalStorage } from 'quasar'

export default {
  name: 'Pagebinproperty',
  data () {
    return {
      openid: '',
      login_name: '',
      authin: '0',
      pathname: 'binproperty/',
      pathname_previous: '',
      pathname_next: '',
      separator: 'cell',
      loading: false,
      height: '',
      table_list: [],
      columns: [
        { name: 'userlevel',
          required: true,
          label: this.$t('community_mall.cm.userlevel'),
          field: row => row.name, align: 'center',
          style:'height:200px;background:#DBDEE3'},
        { name: 'receivingvolume', label: this.$t('community_mall.cm.receivingvolume'), field: 'receivingvolume', align: 'center' },
        { name: 'deliveringamount', label: this.$t('community_mall.cm.deliveringamount'),field: 'deliveringamount', align: 'center' },
        { name: 'users', label: this.$t('community_mall.cm.users'), field:'users', align: 'center' },
        { name: 'useequipment', label: this.$t('community_mall.cm.useequipment'), field:'useequipment', align: 'center' },
        { name: 'purchasemethod', label: this.$t('community_mall.cm.purchasemethod'), field:'purchasemethod', align: 'center' },
      ],
      data:[
        {
          name:this.$t('community_mall.cm.basicuser'),
          receivingvolume: 100,
          deliveringamount: 100,
          users: this.$t('community_mall.cm.unlimited'),
          useequipment: this.$t('community_mall.cm.unlimited'),
          purchasemethod:this.$t('community_mall.cm.noneedtobuy')
        },
        {
          name:this.$t('community_mall.cm.limitedusers'),
          receivingvolume: 1000,
          deliveringamount: 1000,
          users: this.$t('community_mall.cm.unlimited'),
          useequipment: this.$t('community_mall.cm.unlimited'),
        },
        {
          name:this.$t('community_mall.cm.limitedusers'),
          receivingvolume: this.$t('community_mall.cm.unlimited'),
          deliveringamount: this.$t('community_mall.cm.unlimited'),
          users: this.$t('community_mall.cm.unlimited'),
          useequipment:this.$t('community_mall.cm.unlimited'),
        }
      ],
      filter: '',
      pagination: {
        page: 1,
        rowsPerPage: '30'
      }
    }
  },
  methods: {
    getList () {
      var _this = this
      if (LocalStorage.has('auth')) {
        getauth(_this.pathname, {
        }).then(res => {
          _this.table_list = res.results
          _this.pathname_previous = res.previous
          _this.pathname_next = res.next
        }).catch(err => {
          _this.$q.notify({
            message: err.detail,
            icon: 'close',
            color: 'negative'
          })
        })
      } else {
      }
    },
    getListPrevious () {
      var _this = this
      if (LocalStorage.has('auth')) {
        getauth(_this.pathname_previous, {
        }).then(res => {
          _this.table_list = res.results
          _this.pathname_previous = res.previous
          _this.pathname_next = res.next
        }).catch(err => {
          _this.$q.notify({
            message: err.detail,
            icon: 'close',
            color: 'negative'
          })
        })
      } else {
      }
    },
    getListNext () {
      var _this = this
      if (LocalStorage.has('auth')) {
        getauth(_this.pathname_next, {
        }).then(res => {
          _this.table_list = res.results
          _this.pathname_previous = res.previous
          _this.pathname_next = res.next
        }).catch(err => {
          _this.$q.notify({
            message: err.detail,
            icon: 'close',
            color: 'negative'
          })
        })
      } else {
      }
    },
    reFresh () {
      var _this = this
      _this.getList()
    }
  },
  created () {
    var _this = this
    if (LocalStorage.has('openid')) {
      _this.openid = LocalStorage.getItem('openid')
    } else {
      _this.openid = ''
      LocalStorage.set('openid', '')
    }
    if (LocalStorage.has('login_name')) {
      _this.login_name = LocalStorage.getItem('login_name')
    } else {
      _this.login_name = ''
      LocalStorage.set('login_name', '')
    }
    if (LocalStorage.has('auth')) {
      _this.authin = '1'
      _this.getList()
    } else {
      _this.authin = '0'
    }
  },
  mounted () {
    var _this = this
    if (_this.$q.platform.is.electron) {
      _this.height = String(_this.$q.screen.height - 290) + 'px'
    } else {
      _this.height = _this.$q.screen.height - 290 + '' + 'px'
    }
  },
  updated () {
  },
  destroyed () {
  }
}
</script>
