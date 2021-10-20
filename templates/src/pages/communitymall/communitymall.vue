<template>
  <q-page class="flex flex-top">
    <template>
      <div class="q-pa-md">
        <div class="q-gutter-y-md" style="max-width: 100%">
          <q-tabs
          >
            <transition appear enter-active-class="animated zoomIn">
              <q-route-tab v-show="$q.localStorage.getItem('staff_type') !== 'Supplier' &&
                          $q.localStorage.getItem('staff_type') !== 'Customer'
                         " name="cm" :label="$t('community_mall.cm.buySoftware')" icon="img:statics/communitymall/cm.png" to="/communitymall/cm" exact/>
            </transition>
<!--            <transition appear enter-active-class="animated zoomIn">-->
<!--              <q-route-tab v-show="$q.localStorage.getItem('staff_type') !== 'Supplier' &&-->
<!--                          $q.localStorage.getItem('staff_type') !== 'Customer'-->
<!--                         " name="equipment" :label="$t('community_mall.equipment.buyequipment')" icon="img:statics/communitymall/equipment.png" to="/communitymall/equipment" exact/>-->
<!--            </transition>-->
          </q-tabs>
        </div>
      </div>
    </template>
    <div class="main-table3">
      <router-view />
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'upload'
}
</script>

<style scoped>

</style>
