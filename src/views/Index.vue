<!--
 * @Author: Jackie
 * @Date: 2022-05-07 14:31:02
 * @LastEditTime: 2022-05-12 15:38:21
 * @LastEditors: Jackie
 * @Description: file content
 * @FilePath: /vue-admin-Background-template/src/views/Index.vue
 * @version: 
-->
<template>
  <a-layout id="layout">
    <HeaderBar />
    <a-layout>
      <SideBar />
      <a-layout class="wrap" ref="wrapScroll">
        <a-layout-content class="box">
          <router-view />
        </a-layout-content>
      </a-layout>
    </a-layout>
    <!-- <a-layout-footer class="footer"><FooterCopyright /></a-layout-footer> -->
  </a-layout>
</template>
<script>
import SideBar from "@/components/SideBar";
import HeaderBar from "@/components/HeaderBar";
import FooterCopyright from "@/components/FooterCopyright";
export default {
  components: {
    SideBar,
    HeaderBar,
    FooterCopyright,
  },
  data() {
    return {
      collapsed: false,
    };
  },
  watch: {
    $route(to, from) {
      this.$nextTick(() => {
        // 滚动条
        document.querySelector(".wrap").scrollTop = 0;
        //   this.$refs.wrapScroll.scrollTop = scrollTo(0, 0);
      });
    },
  },
  mounted() {},
};
</script>

<style lang="scss" scoped>
#layout {
  height: 100%;
  .wrap {
    margin-left: 15px;
    transition: all 0.5s;
    background-color: #fff;
    padding: 20px;
    /* .content {
      background-color: #fff;
      padding: 24px;
      margin: 0;
      min-height: 100%;
    } */
  }
  .footer {
    background: #fff;
  }
}
</style>
