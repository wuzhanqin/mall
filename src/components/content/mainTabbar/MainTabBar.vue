<template>
	<div>
		<tab-bar>
			<tab-bar-item path="/home" activeColor="blue">
				<img slot="item-icon" src="~assets/img/tabbar/home.png" alt=""/>
				<img slot="item-icon-active" src="~assets/img/tabbar/home_active.png" alt=""/>
				<div slot="item-text">首页</div>
			</tab-bar-item>
			<tab-bar-item path="/category" activeColor="blue">
				<img slot="item-icon" src="~assets/img/tabbar/category.png" alt=""/>
				<img slot="item-icon-active" src="~assets/img/tabbar/category_active.png" alt=""/>
				<div slot="item-text">分类</div>
			</tab-bar-item>
			<tab-bar-item path="/cart" activeColor="blue">
				<img slot="item-icon" src="~assets/img/tabbar/cart.png" alt=""/>
				<img slot="item-icon-active" src="~assets/img/tabbar/cart_active.png" alt=""/>
				<div slot="item-text">购物车</div>
			</tab-bar-item>
			<tab-bar-item path="/profile" activeColor="blue">
				<img slot="item-icon" src="~assets/img/tabbar/profile.png" alt=""/>
				<img slot="item-icon-active" src="~assets/img/tabbar/profile_active.png" alt=""/>
				<div slot="item-text">个人</div>
			</tab-bar-item>
		</tab-bar>
	</div>
</template>

<script>
	import TabBar from 'components/common/tabbar/TabBar'
	import TabBarItem from 'components/common/tabbar/TabBarItem'
	export default{
		name:'MainTabBar',
		components:{
			TabBar,
			TabBarItem
		}
	}
</script>

<style scoped>
</style>