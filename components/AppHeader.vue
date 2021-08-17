<template>
  <header>
    <div class="header-top min-width">
      <div class="container fn-clear">
        <strong class="fn-left">
          Call us：400-000-0000
          <span class="s-time">Serve Time：9:00 - 18:00</span>
        </strong>
        <ul class="header_contact">
          <li class="c_1">
            <a class="ico_head_weixin" id="wx"></a>
          </li>
          <li class="c_2">
            <a href="#" target="_blank" title="官方QQ" alt="官方QQ">
              <b class="ico_head_QQ"></b>
            </a>
          </li>
          <li class="c_4">
            <a href="#" target="_blank" title="新浪微博" alt="新浪微博">
              <b class="ico_head_sina"></b>
            </a>
          </li>
        </ul>

        <!-- 用户未登录 -->
        <ul v-if="!userInfo" class="fn-right header-top-ul">
          <!-- <li><a href="" :class="'c-orange'">测试</a></li> -->
          <li>
            <NuxtLink to="/" :class="{ 'c-orange': $route.fullPath === '/' }"
              >Main</NuxtLink
            >
          </li>
          <li>
            <div class="">
              <NuxtLink
                to="/register"
                :class="{ 'c-orange': $route.fullPath === '/register' }"
              >
                Register
              </NuxtLink>
            </div>
          </li>
          <li>
            <div class="">
              <NuxtLink
                to="/login"
                :class="{ 'c-orange': $route.fullPath === '/login' }"
              >
                Log in
              </NuxtLink>
            </div>
          </li>
        </ul>

        <!-- 用户已登录 -->
        <ul v-if="userInfo" class="fn-right header-top-ul">
          <li><NuxtLink to="/" class="app">Back</NuxtLink></li>
          <li>
            <div class="">
              <NuxtLink to="/user" class="user" title="我的账户">
                <i class="el-icon-user-solid">{{ userInfo.nickName }}</i>
              </NuxtLink>
            </div>
          </li>
          <li>
            <div class="">
              <a
                href="javascript:void(0)"
                class="js-login"
                @click="logout()"
                title="退出"
              >
                Log Out
              </a>
            </div>
          </li>
        </ul>
      </div>
    </div>
    <div class="header min-width">
      <div class="container">
        <div class="fn-left logo">
          <NuxtLink to="/">
            <img src="~/assets/images/logo.png" title="" />
          </NuxtLink>
        </div>
        <ul class="top-nav fn-clear">
          <li :class="{ on: $route.fullPath === '/' }">
            <NuxtLink to="/">Main</NuxtLink>
          </li>
          <li :class="{ on: $route.fullPath === '/list' }">
            <NuxtLink to="/lend"> Invest </NuxtLink>
          </li>
          <li :class="{ on: $route.fullPath === '/help' }">
            <NuxtLink to="/help">Security</NuxtLink>
          </li>
          <li :class="{ on: $route.fullPath === '/about' }">
            <NuxtLink to="/about">About Us</NuxtLink>
          </li>
        </ul>
      </div>
    </div>
  </header>
</template>
<script>
import "~/assets/font/iconfont.css";
import cookie from "js-cookie";

export default {
  data() {
    return {
      userInfo: null,
    };
  },

  mounted() {
    this.showInfo();
  },

  methods: {
    //显示用户信息
    showInfo() {
      let userInfo = cookie.get("userInfo");
      if (!userInfo) {
        console.log("cookie no");
        this.userInfo = null;
        return;
      } else {
        userInfo = JSON.parse(userInfo);
        this.$axios({
          url: "api/core/userInfo/checkToken",
          method: "get",
          headers: {
            token: userInfo.token,
          },
        }).then((response) => {
          this.userInfo = userInfo;
        });
      }
    },

    //退出
    logout() {
      window.location.href = "/login";
      this.userInfo = null;
      cookie.set("userInfo", "");
    },
  },
};
</script>
