<template>
  	<div class="summary-bar" :style="{width: width}">
		<span class="left-part">
			<label class="select-all"><input type="checkbox" name="" v-model="isSelectedAll" @click="selectAll">全选</label>
			<span>删除选中的商品</span>
			<span>移到我的关注</span>
			<span>清空购物车</span>
		</span>
		<span class="right-part">
			<span>已选择{{ selectedProductsNum }}件商品</span>
			<span>总价:￥{{ totalMoney }}</span>
			<span class="pay-it-now">去付款</span>
		</span>
	</div>
</template>

<script>
export default {
  name: 'SummaryBar',
  props: {
  	totalMoney: {
  		type: String,
  		default: 0,
  	},
  	selectedProductsNum: {
  		type: Number,
  		default: 0,
  	},
  	width: {
  		type: String,
  		default: '90%'
  	},
  	isSelectedAll: {
  		type: Boolean,
  		default: false,
  	}
  },
  data () {
    return {
    }
  },
  methods: {
  	selectAll: function () {
  		this.$emit('select-all');
  	},
  },
  computed: {
  },
};
</script>

<style scoped>
	/* 汇总栏 */
	.summary-bar {
		margin: 0 auto;
		height: 50px;
		line-height: 50px;
		font-size: 13px;
		/*cursor: pointer;*/
	}
	.summary-bar .left-part {
		float: left;
	}
	.summary-bar .left-part>* {
		margin-right: 20px;
		cursor: pointer;
	}
	.summary-bar .left-part>*:hover {
		color: #ef1234;
	}
	.summary-bar .left-part input {
		vertical-align: -2px;
		margin-right: 3px;
	}
	.summary-bar .right-part {
		float: right;
	}
	.summary-bar .right-part>* {
		margin-left: 20px;
	}
	.summary-bar .right-part  .pay-it-now {
		background-color: #ef1234;
		display: inline-block;
		/*height: 80%;*/
		padding: 0 10px;
		color: #fff;
		font-size: 16px;
		font-weight: bold;
		cursor: pointer;
	}
</style>
