<script>
	import Item from '../../lib/item.svelte';
	import Body from '../../lib/body.svelte';
	import { A1, A2, B1, B2 } from '../../lib/index';

	let current = A1;

	let active = 'A1';
</script>

<svelte:head>
	<link
		href="https://unpkg.com/tailwindcss@^2/dist/tailwind.min.css"
		rel="stylesheet"
	/></svelte:head
>

<body>
	<main>
		<div class="logo-wrap">
			<img src="logo.png" alt="logo" />
			<p class="motto">İngilizce Rehberiniz</p>
		</div>
		<hr />
		<div class="content">
			<p class="info">
				Aşağıda seviyenizi seçince, o seviye ilgili konular ve bolca alıştırmalar(listening odaklı)
				bulacaksınız.
			</p>
			<div class="levels">
				<button
					class="level"
					class:active={active === 'A1'}
					on:click={() => {
						active = 'A1';
						current = A1;
					}}
				>
					A1
				</button>
				<button
					class="level"
					class:active={active === 'A2'}
					on:click={() => {
						active = 'A2';
						current = A2;
					}}>A2</button
				>
				<button
					class="level"
					class:active={active === 'B1'}
					on:click={() => {
						active = 'B1';
						current = B1;
					}}>B1</button
				>
				<button
					class="level"
					class:active={active === 'B2'}
					on:click={() => {
						active = 'B2';
						current = B2;
					}}>B2</button
				>
			</div>

			<p></p>
			<div class="space-y-4">
				<Body bind:active>
					{#each current as { url, topic, recap }, i}
						<Item id={i} title={i + 1} subTitle={'• ' + topic}>
							<h1>
								{recap}
							</h1>
							<p class="url"><a href={url} target="_blank">Detayla konu anlatımına git</a></p>
						</Item>
					{/each}
				</Body>
			</div>
		</div>
	</main>
</body>

<style>
	* {
		margin: 0;
		padding: 0;
	}
	body {
		background-color: antiquewhite;
		background: url("https://raw.githubusercontent.com/alisaydam/ingilizcerehberim/main/static/bg.jpg");
		background-repeat: no-repeat;
		background-size: cover;
		height: 100vh;
		width: 100%;
		font-family: Verdana, Geneva, Tahoma, sans-serif;
		color: #616161;
	}
	main {
		max-width: 1000px;
		background: white;
		height: 100%;
		margin: auto;
		margin-top: 50px; 
	}
	img {
		height: 120px;
	}
	.content {
		padding: 10px;
		background-color: white;
		margin-top: 50px; 
	}
	.logo-wrap {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.motto {
		font-family: cursive;
		font-size: 20px;
		font-weight: 500;
		padding-right: 150px;
	}
	.info {
		margin: 10px 0;
	}
	.levels {
		display: flex;
		width: 100%;
		justify-content: space-around;
		gap: 1px;
	}
	.level {
		background-color: #fefae0;
		flex-basis: 100%;
		padding: 10px;
		text-align: center;
		border-radius: 10px;
		cursor: pointer;
		border: none;
	}
	.level:hover {
		background-color: #faedcd;
	}
	.active {
		background-color: #faedcd;
	}
	h1 {
		padding: 15px 20px;
		color: #616161;
	}
	.url {
		padding: 10px 20px;
		background-color: #e9edc9;
		width: fit-content;
		border-radius: 10px;
		margin-left: 20px;
	}
</style>
