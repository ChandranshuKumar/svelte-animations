<script lang="ts">
	import { fade, blur, fly, slide, scale } from 'svelte/transition';

	let showFadeBlock = false;
	let showBlurBlock = false;
	let showFlyBlock = false;
	let showSlideBlock = false;
	let showScaleBlock = false;
</script>

<div class="wrapper">
	<div class="fade">
		<h3>fade</h3>
		<button on:click={() => (showFadeBlock = !showFadeBlock)}
			>Show Fade {showFadeBlock ? 'Out' : 'In'} Effect</button
		>
		{#if showFadeBlock}
			<div class="tansition-block" transition:fade|local>
				<p>This is fade transition</p>
			</div>
		{/if}
	</div>

	<div class="blur">
		<h3>blur</h3>
		<button on:click={() => (showBlurBlock = !showBlurBlock)}
			>Show Blur {showBlurBlock ? 'Out' : 'In'} Effect</button
		>
		{#if showBlurBlock}
			<div class="tansition-block" transition:blur>
				<p>This is blur transition</p>
			</div>
		{/if}
	</div>

	<div class="fly">
		<h3>fly</h3>
		<button on:click={() => (showFlyBlock = !showFlyBlock)}
			>Show Fly {showFlyBlock ? 'Out' : 'In'} Effect</button
		>
		{#if showFlyBlock}
			<div class="tansition-block" in:fly={{ x: 200 }} out:fly={{ x: -200 }}>
				<p>This is fly transition</p>
			</div>
		{/if}
	</div>

	<div class="slide">
		<h3>slide</h3>
		<button on:click={() => (showSlideBlock = !showSlideBlock)}
			>Show Slide {showSlideBlock ? 'Out' : 'In'} Effect</button
		>
		{#if showSlideBlock}
			<div class="tansition-block" transition:slide>
				<p>This is slide transition</p>
			</div>
		{/if}
	</div>

	<div class="scale">
		<h3>scale</h3>
		<button on:click={() => (showScaleBlock = !showScaleBlock)}
			>Show Scale {showScaleBlock ? 'Out' : 'In'} Effect</button
		>
		{#if showScaleBlock}
			<div class="tansition-block" transition:scale>
				<p>This is scale transition</p>
			</div>
		{/if}
	</div>
</div>

<style lang="scss">
	:global(body) {
		margin: 0;
		padding: 0;
		background-color: #eee;
	}

	button {
		margin-bottom: 1rem;
		padding: 0.5rem;
		display: block;
	}

	.tansition-block {
		padding: 1rem;
		box-sizing: border-box;
		background-color: #fff;
		max-width: 20rem;
		border-radius: 0.5rem;
	}

	.wrapper {
		> * {
			height: 15rem;
		}
		padding: 1rem;
		box-sizing: border-box;
		.fade,
		.blur,
		.fly,
		.slide,
		.scale {
			padding: 1rem;
		}
	}
</style>
