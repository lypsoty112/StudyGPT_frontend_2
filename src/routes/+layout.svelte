<script lang="ts">
	import '../app.postcss';
	import '../app.postcss';

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup, initializeStores, Toast, Modal } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });
	import { AppShell } from '@skeletonlabs/skeleton';
	import Navbar from '../components/navbar.svelte';
	import Footer from '../components/footer.svelte';

	initializeStores();
	let maxToast = 5;
</script>

<Toast position="br" zIndex="z-50" shadow="shadow-lg" max={maxToast} />
<Modal />

<AppShell>
	<svelte:fragment slot="header">
		<Navbar />
	</svelte:fragment>
	<!-- (sidebarLeft) -->
	<!-- (sidebarRight) -->
	<!-- (pageHeader) -->
	<!-- Router Slot -->
	<main>
		<slot />
	</main>
	<!-- ---- / ---- -->
	<!-- (pageFooter) -->
</AppShell>
