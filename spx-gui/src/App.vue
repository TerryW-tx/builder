<!--
 * @Author: xuning
 * @Date: 2024-01-12 11:15:15
 * @LastEditors: Xu Ning
 * @LastEditTime: 2024-01-24 17:47:21
 * @FilePath: /builder/spx-gui/src/App.vue
 * @Description:
-->
<template>
  <div id="spx">
    <n-config-provider :theme-overrides="themeOverrides">
      <n-message-provider>
        <n-layout embedded>
          <n-layout-header>
            <TopMenu />
          </n-layout-header>
          <n-layout-content>
            <router-view />
          </n-layout-content>
        </n-layout>
      </n-message-provider>
    </n-config-provider>
  </div>
</template>

<script setup lang="ts">
import {
  NConfigProvider,
  NMessageProvider,
  NLayout,
  NLayoutHeader,
  NLayoutContent,
} from "naive-ui";
import TopMenu from "@/components/top-menu/TopMenu.vue";
import "@/assets/theme.ts";
/**
 * @description: Override spx-gui theme
 * @return {*}
 */
const themeOverrides = {
  common: {
    primaryColor: "#FF7E6C",
    fontWeightStrong: "600",
  },
  Button: {
    color: "#ED729EFF",
    colorHover: "#FF7CB5FF",
    colorPressed: "#F1518AFF",
    colorFocus: "#F1518AFF",
    colorDisabled: "#0000",
    textColorHover: "#FFFFFFFF",
    textColorPressed: "#FFFFFFFF",
    textColorFocus: "#FFFFFFFF",
    textColor: "rgba(255, 255, 255, 1)",
    borderHover: "1px solid #FF7CB5FF",
    borderPressed: "1px solid #F1518AFF",
    borderFocus: "1px solid #F1518AFF",
    borderRadiusTiny: "25px",
    borderRadiusSmall: "25px",
    borderRadiusMedium: "25px",
    borderRadiusLarge: "25px",
    border: "1px solid #ED729E",
  },
  Select: {
    peers: {
      InternalSelection: {
        textColor: "#FF0000",
      },
    },
  },
  Input: {
    caretColor: "#F1518A",
    borderHover: "1px solid #F1518A",
    border: "1px solid #ED729E",
    borderFocus: "1px solid #F1518A",
  },
  Dropdown: {
    color: "#fff",
    optionTextColor: "rgb(51, 54, 57)",
    dividerColor: "rgb(239, 239, 245)",
    // optionColorHover: "#E87FA74A",
    prefixColor: "rgb(51, 54, 57)",
    suffixColor: "rgb(51, 54, 57)",
    optionColorActive: "rgba(24, 160, 88, 0.1)",
    // optionTextColorHover: "#E87FA7FF",
    borderRadius: "15px",
    optionTextColorActive: "#18a058",
    optionTextColorChildActive: "#18a058",
    optionColorHoverInverted: "#18a058",
    optionColorActiveInverted: "#18a058",
  },
  Switch: {
    railColorActive: "#ED729E",
  },
};
</script>

<style lang="scss">
@import "./assets/fonts/font.css";
@import "./assets/theme.scss";

#spx {
  height: 100%;
  background: linear-gradient(180deg, #ffffff, $yellow-background-color);
}

body {
  font-family: ChauPhilomeneOne, AlibabaPuHuiT, sans-serif;
}

:lang(en) {
  font-size: 15.8px;
  line-height: 1.6;
}

:lang(zh) {
  font-size: 16px;
  line-height: 1.6;
}

.n-layout-header {
  background: #696a5a;
  height: 60px;
  padding: 13px;
}

.n-layout {
  height: 100%;
  background: #ffffff00;
}

.n-menu,
.n-menu--horizontal,
.n-menu--responsive {
  --n-item-height: 38px !important;
}
.n-menu.n-menu--horizontal .n-menu-item-content {
  padding: 0;
}

.v-overflow {
  width: 100%;
  display: flex;
  overflow: hidden;
  flex-direction: row;
  justify-content: space-around;
}
</style>
