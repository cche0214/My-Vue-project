<template>
  <nav>
    <router-link to="/home" class="active">首页</router-link>
    <router-link to="/view">地图展示</router-link>
    <router-link to="/story">革命故事</router-link>
    <router-link to="/new">实践新闻</router-link>
    <router-link to="/experience">感悟心得</router-link>
    <router-link to="/about">关于本站</router-link>
    <router-link to="/message">意见留言</router-link>
  </nav>
</template>

<script>
export default {

}
</script>

<style scoped>
  nav {
    display: flex;
    justify-content: center;
    background: rgb(30,50,100);
    padding: 5px 0;
  }
  nav a {
    color:white;
    padding: 10px 30px;
    text-decoration: none;
    font-size: 16px;
  }
  nav a.router-link-active {
    background-color: rgba(173, 216, 230, 0.6); /* 淡蓝色背景 */
  }
  nav a:hover {
    color: #ff9900;
  }
</style>