<template>
	<div class="goods-item" @click="itemClick">
		<img v-lazy="showImage" alt="" @load="imageLoad">
		<div class="goods-info">
			<p>{{goodsItem.title}}</p>
			<span class="price">{{goodsItem.price}}</span>
			<span class="collect">{{goodsItem.cfav}}</span>
		</div>
	</div>
</template>

<script>
	export default{
		name:'GoodsListItem',
		props:{
			goodsItem:{
				type:Object,
				default(){
					return {}
				}
			}
		},
        computed:{
            showImage(){
                return this.goodsItem.image || this.goodsItem.show.img
            }
        },
        methods:{
            imageLoad(){
                //if(this.$route.path.indexOf('/home')){
                    this.$bus.$emit('itemImageLoad')
                //}
            },
            itemClick(){
                this.$router.push('./detail/'+this.goodsItem.iid)
            }
        }
	}
</script>

<style scoped>
	.goods-item {
        position: relative;
        padding-bottom: 40px;
        width: 48%;
    }
    .goods-item img {
        width: 100%;
        height: 100%;
        border-radius: 6px;
    }
    .goods-info {
        position: absolute;
        left: 0;
        right: 0;
        bottom: 8px;
        font-size: 12px;
        overflow: hidden;
        text-align: center;
    }
    .goods-info p{
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
        margin-bottom: 3px;
    }
    .goods-info .price {
        color: var(--color-high-text);
        margin-right: 20px;
    }
    .goods-info .collect {
        position: relative;
    }
    .goods-info .collect::before{
        content: '';
        position: absolute;
        left: -15px;
        top: -1px;
        width: 14px;
        height: 14px;
        background: url("~assets/img/common/collect.svg") 0 0/14px 14px;
    }
</style>