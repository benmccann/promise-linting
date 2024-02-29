<script lang="ts">
	import Child from './Child.svelte';

	const promiseFunc: () => Promise<void> = async () => {};

	// pnpm lint will identify this as an issue as it should
	const func: () => void = promiseFunc;
	func();
</script>

<!-- pnpm lint will not identify this as an issue, but it should -->
<Child func={promiseFunc} />
