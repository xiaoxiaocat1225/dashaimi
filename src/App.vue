<!-- <script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";
</script>

<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="@/assets/logo.svg"
      width="125"
      height="125"
    />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">主页</RouterLink>
        <RouterLink to="/about">关于我们</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style> -->

<template>
  <a-layout style="min-height: 100vh">
    <!-- 这是左边那一块的内容 -->
    <a-layout-sider v-model:collapsed="collapsed" collapsible>
      <div class="logo" />
      <a-menu v-model:selectedKeys="selectedKeys" theme="dark" mode="inline">
        <!-- 这是一个菜单里的选项 -->
        <a-sub-menu key="sub3">
          <template #title>
            <span>
              <!-- <user-outlined /> -->
              <slack-outlined />
              <span>地图显示</span>
            </span>
          </template>
          <a-menu-item key="31">
            <RouterLink to="/about">行政图</RouterLink>
          </a-menu-item>
          <a-menu-item key="32">卫星图</a-menu-item>
          <a-menu-item key="33">专题图</a-menu-item>
        </a-sub-menu>
        <!-- 这是二个菜单里的选项 -->

        <a-menu-item key="2">
          <desktop-outlined />
          <span>表单交互</span>
        </a-menu-item>
        <a-sub-menu key="sub1">
          <template #title>
            <span>
              <user-outlined />
              <span>User</span>
            </span>
          </template>
          <a-menu-item key="3">Tom</a-menu-item>
          <a-menu-item key="4">Bill</a-menu-item>
          <a-menu-item key="5">Alex</a-menu-item>
        </a-sub-menu>
        <a-sub-menu key="sub2">
          <template #title>
            <span>
              <team-outlined />
              <span>Team</span>
            </span>
          </template>
          <a-menu-item key="6">Team 1</a-menu-item>
          <a-menu-item key="8">Team 2</a-menu-item>
        </a-sub-menu>
        <a-menu-item key="9">
          <file-outlined />
          <span>File</span>
        </a-menu-item>
      </a-menu>
    </a-layout-sider>
    <!-- 这是右边那一块的内容 -->
    <a-layout>
      <a-layout-header style="background: blue; padding: 0" />
      <a-layout-content style="margin: 10px 16px">
        <div
          :style="{ padding: '24px', background: '#fff', minHeight: '360px' }"
        >
          <!-- Bill is a cat. -->
          <RouterView />
        </div>
      </a-layout-content>
      <a-layout-footer style="text-align: center">
        webgis progarm ©2018 Created by zafu edu
      </a-layout-footer>
    </a-layout>
  </a-layout>
</template>
<script>
import {
  SlackOutlined,
  PieChartOutlined,
  DesktopOutlined,
  UserOutlined,
  TeamOutlined,
  FileOutlined,
} from "@ant-design/icons-vue";
import { defineComponent, ref } from "vue";
export default defineComponent({
  components: {
    SlackOutlined,
    PieChartOutlined,
    DesktopOutlined,
    UserOutlined,
    TeamOutlined,
    FileOutlined,
  },

  data() {
    return {
      collapsed: ref(false),
      selectedKeys: ref(["1"]),
    };
  },
});
</script>
<style>
#components-layout-demo-side .logo {
  height: 32px;
  margin: 16px;
  background: rgba(255, 255, 255, 0.3);
}

.site-layout .site-layout-background {
  background: #fff;
}
[data-theme="dark"] .site-layout .site-layout-background {
  background: #141414;
}
</style>
