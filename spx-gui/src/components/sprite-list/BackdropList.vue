<!--
 * @Author: Xu Ning
 * @Date: 2024-01-18 17:08:16
 * @LastEditors: Xu Ning
 * @LastEditTime: 2024-01-24 11:52:58
 * @FilePath: /builder/spx-gui/src/components/sprite-list/BackdropList.vue
 * @Description: 
-->
<template>
  <div class="stage-list">
    Stage
    <div class="stage-list-space">
      <SpriteAddBtn :type="'bg'" />
      <ImageCardCom
        :type="'bg'"
        :asset="backdrop"
        :style="{ 'margin-bottom': '26px' }"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed, ComputedRef } from "vue";
import { useBackdropStore } from "@/store/modules/backdrop";
import ImageCardCom from "@/components/sprite-list/ImageCardCom.vue";
import SpriteAddBtn from "@/components/sprite-list/SpriteAddBtn.vue";
import Backdrop from "@/class/backdrop";

// ----------props & emit------------------------------------
const backdropStore = useBackdropStore();

// ----------computed properties-----------------------------
// Computed backdrop from backdropStore.
const backdrop : ComputedRef<Backdrop> = computed(() => backdropStore.backdrop as Backdrop);
</script>

<style scoped lang="scss">
.stage-list {
  text-align: center;
  height: calc(100% - 20px);
  padding: 10px;
  .stage-list-space {
    background: white;
    box-shadow: 0 5px 5px 0 #00000019;
    margin: 0 10px;
    height: calc(100% - 20px);
    overflow: scroll;
    border-radius: 20px;
  }
}
</style>
