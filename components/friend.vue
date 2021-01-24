<template>
	<div class="friend">
		<div class="avatar">
			<a-avatar
				shape="square"
				:size="60"
				src="https://lh3.googleusercontent.com/ogw/ADGmqu-xqftvy082_OYEocVJFIBoBoH59yReuyWDps4Y=s64-c-mo"
			>
			</a-avatar>
		</div>
		<a class="name" href="href">Luis Sousa</a>
		<span class="phone">936144559</span>
		<span class="email">lula.sousa@gmail.com</span>
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
	name: "friend",
	components: {
		AAvatar: Avatar,
		ATag: Tag,
	},
};
</script>

<style lang="less" scoped>
.friend {
	display: grid;
	grid-template-columns: repeat(8, 1fr);
	grid-template-rows: repeat(3, 1fr);
	gap: 0px 0px;
	grid-template-areas:
		"avatar avatar name name name name money money"
		"avatar avatar phone phone phone phone money money"
		"avatar avatar email email email email money money";
	margin: 4px 0;
	.avatar {
		grid-area: avatar;
		display: flex;
		align-items: center;
	}

	.name {
		grid-area: name;
	}

	.phone {
		grid-area: phone;
		color: grey;
	}

	.email {
		grid-area: email;
	}

	.money {
		grid-area: money;
		display: flex;
		align-items: center;
		justify-content: flex-end;
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
