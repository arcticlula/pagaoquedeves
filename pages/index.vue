<template>
	<div class="grid-container">
		<div class="header">
			<div class="money">
				<a-tag color="#52C41A" class="money-box">
					<span class="money-box-text">- 20€</span>
				</a-tag>
			</div>
			<div class="user">
				<a-avatar icon="user" />
				<span class="user-name">Luis Sousa</span>
			</div>
		</div>
		<div class="content">
			<a-tabs v-model="mainTab" size="small">
				<a-tab-pane class="content-tab" key="1">
					<span slot="tab">
						<a-icon type="history" />
						<span v-if="mainTab === '1'">Actividade</span>
					</span>
					<activity />
				</a-tab-pane>
				<a-tab-pane key="2">
					<span slot="tab">
						<a-icon type="credit-card" />
						<span v-if="mainTab === '2'">Despesas</span>
					</span>
					<expenses class="content-tab" />
				</a-tab-pane>
				<a-tab-pane key="3">
					<span slot="tab">
						<a-icon type="team" />
						<span v-if="mainTab === '3'">Amigos</span>
					</span>
					<friends class="content-tab" />
				</a-tab-pane>
			</a-tabs>
		</div>
		<div class="footer">
			Copyright © {{ $dateFns.format(new Date(), "yyyy") }} Luis Sousa™
		</div>
	</div>
</template>

<script>
import { Avatar, Divider, Icon, Menu, Tabs, Tag } from "ant-design-vue";
import activity from "./activity";
import expenses from "./expenses";
import friends from "./friends";
export default {
	components: {
		activity,
		expenses,
		friends,
		AAvatar: Avatar,
		ADivider: Divider,
		AIcon: Icon,
		ATabs: Tabs,
		ATabPane: Tabs.TabPane,
		ATag: Tag,
	},
	data() {
		return {
			mainTab: "2",
			friendsTab: "a",
		};
	},
	methods: {},
};
</script>

<style lang="less" scoped>
@import (reference) "~/assets/variables.less";
html,
body,
.grid-container {
	height: 100vh;
	margin: 0;
}

.grid-container {
	display: grid;
	grid-template-columns: repeat(5, 1fr);
	grid-template-rows: 40px repeat(7, 1fr) 0.5fr;
	gap: 0px 0px;
	grid-template-areas:
		"header header header header header"
		"content content content content content"
		"content content content content content"
		"content content content content content"
		"content content content content content"
		"content content content content content"
		"content content content content content"
		"content content content content content"
		"footer footer footer footer footer";
	.header {
		display: grid;
		grid-template-columns: repeat(5, 1fr);
		grid-template-rows: 40px;
		gap: 0px 0px;
		grid-template-areas: "money . . user user";
		grid-area: header;
		height: 40px;
		background-color: @primary-color;
		color: white;
	}
	.money {
		grid-area: money;
		display: flex;
		align-items: center;
		margin-left: 20px;
		.money-box {
			display: flex;
			align-items: center;
			justify-content: center;
			width: 50px;
			height: 25px;
			box-shadow: 1px 1px rgba(0, 0, 0, 0.5);
			.money-box-text {
				font-weight: bold;
			}
		}
	}

	.user {
		grid-area: user;
		display: flex;
		align-items: center;
		justify-content: flex-end;
		.user-img {
			height: 32px;
			width: 32px;
			border-radius: 50%;
		}
		.user-name {
			margin: 0 16px 0 8px;
		}
	}
	.content {
		grid-area: content;
		// .content-tab {
		// 	&:first-child {
		// 		padding-top: 8px;
		// 	}
		// }
	}
	.footer {
		grid-area: footer;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 10px;
		color: grey;
	}
	.ant-menu-horizontal {
		line-height: 32px;
	}
}

/* For presentation only, no need to copy the code below */
/* .grid-container * {
	border: 1px solid red;
} */
</style>
