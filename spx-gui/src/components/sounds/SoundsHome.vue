<!--
 * @Author: Yao xinyue kother@qq.com
 * @Date: 2024-01-12 17:27:57
 * @LastEditors: Xu Ning
 * @LastEditTime: 2024-01-24 18:02:58
 * @FilePath: /builder/spx-gui/src/components/sounds/SoundsHome.vue
 * @Description: Sounds Homepage, includes Edit Part And Card List
-->
<template>
  <n-layout has-sider style="height: calc(100vh - 60px - 54px - 12px)">
    <n-layout-sider
      :native-scrollbar="false"
      content-style="paddingLeft: 110px;"
      style="width: 175px"
    >
      <SoundsEditCard
        v-for="asset in assets"
        :key="asset.id"
        :asset="asset"
        :style="{ 'margin-bottom': '26px' }"
      />
    </n-layout-sider>
    <n-layout-content>
      <SoundsEdit style="margin-left: 10px" />
    </n-layout-content>
  </n-layout>
</template>

<script lang="ts" setup>
import SoundsEditCard from "@/components/sounds/SoundsEditCard.vue";
import { NLayout, NLayoutContent, NLayoutSider } from "naive-ui";
import SoundsEdit from "@/components/sounds/SoundsEdit.vue";
import { Asset } from "@/interface/library.ts";
import { onMounted, ref } from "vue";
import { getAssetList } from "@/api/asset.ts";
import { AssetType } from "@/constant/constant.ts";

const assets = ref<Asset[]>([]);

onMounted(async () => {
  try {
    const pageIndex = 1;
    const pageSize = 10;
    const response = await getAssetList(pageIndex, pageSize, AssetType.Sounds);
    assets.value = response.data;
  } catch (error) {
    console.error("Error fetching assets:", error);
  }
});
</script>

<style scoped lang="scss">
</style>
