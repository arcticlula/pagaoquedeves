<template>
	<div class="activity">
		<a-config-provider>
			<template #renderEmpty>
				<div style="text-align: center">
					<a-icon type="frown" style="font-size: 20px" />
					<p>Sem Resultados</p>
				</div>
			</template>
			<a-list size="small" item-layout="vertical" class="config-provider">
				<a-list-item>
					<activity />
				</a-list-item>
			</a-list>
		</a-config-provider>
	</div>
</template>

<script>
import { ConfigProvider, Icon, List } from "ant-design-vue";
import activity from "~/components/activity.vue";
export default {
	components: {
		activity,
		AConfigProvider: ConfigProvider,
		AIcon: Icon,
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
