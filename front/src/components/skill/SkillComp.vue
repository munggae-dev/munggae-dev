<template>
	<v-row
		no-gutters
		style="padding: 10px 0"
		align="center"
		justify="start"
		@click="$emit('click')">
		<v-col cols="2">
			<h2 :style="`color : ${skill.color}`">{{ skill.name }}</h2>
		</v-col>
		<v-col>
			<v-progress-linear
				:value="skill.score"
				height="25"
				rounded
				:color="skill.color">
				<!-- eslint-disable-next-line -->
				<template v-slot:default="{ value }">
					<strong class="cwhite">{{ Math.ceil(skill.score) }}%</strong>
				</template>
			</v-progress-linear>
		</v-col>
		<v-col cols="1">
			<h2>
				{{ skill.experience }}
			</h2>
		</v-col>
	</v-row>
</template>

<script>
	export default {
		name: "SkillComp",
		props: {
			skill: {
				type: Object,
				required: true,
				default: () => {
					return {
						name: "Python",
						score: 5,
						experience: "상",
						color: "blue",
					};
				},
			},
		},
		components: {},
		data: () => ({}),
		computed: {},
		methods: {},
		watch: {},
	};
</script>

<style scoped>
	.col {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.cwhite {
		color: white;
	}
</style>
