<template>
    <div class='Home'>
        <el-container>
			<!-- 这里是每个页面共同的头 -->
            <el-header>
				<!-- 首页 实时监测 数据分析 数据统计 系统管理 -->
				<div class="HomeNav">
					<div>首页</div>
					<div>实时监测</div>
					<div>数据分析</div>
					<span>上海博物馆监控平台</span>
					<div>数据统计</div>
					<div>系统管理</div>
				</div>
            </el-header>
            <!--下面是各个不同的页面-->
			<router-view></router-view>
        </el-container>
    </div>
</template>

<script>
export default {
  data () {
    return {
      // 被激活的链接地址
      activePath: ''
    }
  },
  methods: {
    handleCommandMore (command) {
      if (command === 'q') {
        window.sessionStorage.clear()
        this.$router.push('/login')
      }
    },
    saveNavState (activepath) {
      window.sessionStorage.setItem('activePath', activepath)
    }
  }
}
</script>

<style scoped>
.Home{
  width:100%;
  height:100%;
  background-image: url('../assets/image/bg／two.png');
  background-size: 100% 100%;
}
.el-container{
  height: 100%;
  width: 100%;
}
.el-header{
  padding: 0;
  height: 8.8% !important;
}
.HomeNav{
	display: flex;
	justify-content: space-between;
}
</style>
