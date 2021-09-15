<template>
<div class="root">
	<v-header></v-header>
	<v-checklist></v-checklist>
</div>	
</template>

<script>
import vHeader from '@/components/header.vue';
import vChecklist from '@/components/Checklist.vue';
export default {
	name: 'Home',
	components: {
		vHeader,vChecklist
	}
}
</script>

<style scoped="scoped">

</style>
