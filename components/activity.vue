<template>
	<div class="activity">
		<div class="avatar">
			<a-avatar
				:size="60"
				src="https://lh3.googleusercontent.com/ogw/ADGmqu-xqftvy082_OYEocVJFIBoBoH59yReuyWDps4Y=s64-c-mo"
			>
			</a-avatar>
		</div>
		<a class="name" href="href">Luis Sousa</a>
		<span class="data">2020/01/15</span>
		<!-- <span class="description"
			>Lorem ipsum dolor sit amet consectetur adipisicing elit. Iste animi
			consectetur
		</span> -->
		<span class="description">Lorem ipsum dolor sit amet consectur </span>
		<div class="money">
			<a-tag color="#FA541C" class="money-box">
				<span class="money-box-text">- 20€</span>
			</a-tag>
		</div>
	</div>
</template>

<script>
import { Avatar, Tag } from "ant-design-vue";
export default {
	name: "activity",
	components: {
		AAvatar: Avatar,
		ATag: Tag,
	},
};
</script>

<style lang="less" scoped>
@import (reference) "~/assets/variables.less";
.activity {
	display: grid;
	grid-template-columns: repeat(7, 1fr);
	grid-template-rows: 20px 1fr;
	gap: 0px 0px;
	grid-template-areas:
		"avatar name name name data data money"
		"avatar description description description description description money";
	margin-bottom: 8px;
	padding: 0.5rem;
	border: 1px solid @avatar-bg;
	border-radius: 4px;
	background-color: white;
	.avatar {
		grid-area: avatar;
		display: flex;
		align-items: center;
		margin-right: 8px;
	}
	.name {
		grid-area: name;
	}
	.data {
		grid-area: data;
		display: flex;
		align-items: flex-end;
		justify-content: flex-end;
		font-size: 12px;
		color: fade(grey, 50%);
	}
	.description {
		grid-area: description;
		word-break: break-all;
		font-size: 12px;
		color: grey;
		text-align: justify;
	}
	.money {
		grid-area: money;
		display: flex;
		align-items: center;
		justify-content: flex-end;
		margin-left: 8px;
		.money-box {
			display: flex;
			align-items: center;
			justify-content: center;
			min-width: 50px;
			height: 25px;
			.money-box-text {
				font-weight: bold;
			}
		}
	}
	.ant-tag {
		margin-right: 0px;
	}
}
</style>
