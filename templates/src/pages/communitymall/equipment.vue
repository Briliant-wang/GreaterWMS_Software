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
          <q-card>
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
      height: ''
    }
  },
  mounted () {
    var _this = this
    if (_this.$q.platform.is.electron) {
      _this.height = String(_this.$q.screen.height - 200) + 'px'
    } else {
      _this.height = _this.$q.screen.height - 200 + '' + 'px'
    }
  },
  updated () {
  },
  destroyed () {
  }
}
</script>
