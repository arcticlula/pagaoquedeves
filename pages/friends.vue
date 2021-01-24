<template>
	<div>
		<a-input-search
			allow-clear
			placeholder="Procurar por email / username"
			@search="onSearch"
		>
			<a-icon slot="prefix" type="user" />
		</a-input-search>
		<a-divider />
		<a-config-provider>
			<template #renderEmpty>
				<div style="text-align: center">
					<a-icon type="frown" style="font-size: 20px" />
					<p>Sem Resultados</p>
				</div>
			</template>
			<a-list size="small" item-layout="vertical" class="config-provider">
				<a-list-item>
					<friend />
				</a-list-item>
			</a-list>
		</a-config-provider>
	</div>
</template>

<script>
import { ConfigProvider, Divider, Icon, Input, List } from "ant-design-vue";
import friend from "~/components/friend.vue";
export default {
	components: {
		friend,
		AConfigProvider: ConfigProvider,
		ADivider: Divider,
		AIcon: Icon,
		AInputSearch: Input.Search,
		AList: List,
		AListItem: List.Item,
	},
	data() {
		return {};
	},
	methods: {
		onSearch(event) {
			console.log(event);
		},
	},
};
</script>

<style lang="less" scoped>
@import (reference) "~/assets/variables.less";
</style>
