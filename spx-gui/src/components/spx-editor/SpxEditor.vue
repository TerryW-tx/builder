<!--
 * @Author: Yao xinyue
 * @Date: 2024-01-22 11:17:08
 * @LastEditors: Xu Ning
 * @LastEditTime: 2024-01-24 18:05:02
 * @FilePath: /builder/spx-gui/src/components/spx-editor/SpxEditor.vue
 * @Description: 
-->
<template>
  <n-tabs type="card" v-model:value="currentTab" animated>
    <!--Tab Code Part-->
    <n-tab-pane name="code">
      <template #tab>
        <div v-if="currentTab === 'code'" class="tab-container">
          <img class="tab-icon" src="@/assets/icon/code/tab-code-check.svg" />
          <div class="tab-font-check">{{ $t("tab.code") }}</div>
        </div>
        <div v-else class="tab-container">
          <img class="tab-icon" src="@/assets/icon/code/tab-code-uncheck.svg" />
          <div class="tab-font-uncheck">{{ $t("tab.code") }}</div>
        </div>
      </template>
      <!-- TODO Code Editor Part   -->
      <CodeEditorHome />
    </n-tab-pane>
    <!--Tab Sound Part-->
    <n-tab-pane name="sound">
      <template #tab>
        <div v-if="currentTab === 'sound'" class="tab-container">
          <img class="tab-icon" src="@/assets/icon/sound/tab-music-check.svg" />
          <div class="tab-font-check">{{ $t("tab.sound") }}</div>
        </div>
        <div v-else class="tab-container">
          <img
            class="tab-icon"
            src="@/assets/icon/sound/tab-music-uncheck.svg"
          />
          <div class="tab-font-uncheck">{{ $t("tab.sound") }}</div>
        </div>
      </template>
      <!--  S Component SoundsEditHome-->
      <SoundsEditHome />
      <!--  E Component SoundsEditHome-->
    </n-tab-pane>
  </n-tabs>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { NTabs, NTabPane } from "naive-ui";
import SoundsEditHome from "@/components/sounds/SoundsHome.vue";
import CodeEditorHome from "@/components/code-editor/CodeEditorHome.vue";

const currentTab = ref("code");
</script>

<style scoped lang="scss">
@import "@/assets/theme.scss";

.tab-container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.tab-font-uncheck {
  // font-size: 20px;
  color: $spx-editor-tab-font-uncheck;
}

.tab-font-check {
  // font-size: 20px;
  color: $spx-editor-tab-font-check;
}

.tab-icon {
  width: 20px;
  height: 20px;
  margin-right: 5px;
}
</style>
