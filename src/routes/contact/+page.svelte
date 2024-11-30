<script lang="ts">
	import { fade } from 'svelte/transition';

	let email: string = 'hannig.sebi@proton.me';
	let showTooltip: boolean = false;

	function copyToClipboard(): void {
		navigator.clipboard
			.writeText(email)
			.then(() => {
				console.log('Text copied to clipboard!');
				showTooltip = true;
				setTimeout(() => {
					showTooltip = false;
				}, 300); // Hide tooltip after 2 seconds
			})
			.catch((err) => {
				console.error('Failed to copy text to clipboard: ', err);
			});
	}
</script>

<h1>Contact</h1>
<p>You can contact me using github or email:</p>
<br />
<ul>
	<li>
		<a href="http://github.com/CrativeMan" target="_blank" rel="noopener noreferrer" class="link">
			<button>
				<p>Github</p>
			</button>
		</a>
	</li>
	<li class="tooltip-container">
		<button on:click={copyToClipboard}>
			<p>hannig.sebi@proton.me</p>
		</button>
		{#if showTooltip}
			<span class="tooltip" out:fade={{ duration: 300 }}>Copied!</span>
		{/if}
	</li>
</ul>

<style>
	ul {
		display: table;
		margin: 0 auto;
		text-align: center;
	}

	li {
		margin-bottom: var(--size-3);
	}

	.tooltip-container {
		position: relative;
		display: inline-block;
	}

	.tooltip {
		visibility: visible;
		width: 80px;
		background-color: var(--stone-7);
		color: #fff;
		text-align: center;
		border-radius: 5px;
		padding: 5px;
		position: absolute;
		z-index: 1;
		top: 125%; /* Position the tooltip below the button */
		left: 50%;
		margin-left: -40px;
		opacity: 0.9;
	}

	.tooltip::after {
		content: '';
		position: absolute;
		bottom: 100%; /* At the top of the tooltip */
		left: 50%;
		margin-left: -5px;
		border-width: 5px;
		border-style: solid;
		border-color: transparent transparent var(--stone-7) transparent;
	}
</style>
