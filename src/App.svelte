

<script>
	import App from "./App.svelte"
	import gsap from 'gsap';
	import { onMount } from 'svelte'

	let title = "Café des Devs";
	let message;
	let form = document.querySelector('.text__input')
	let container;

	let btns = document.querySelectorAll('#btn1 #btn2 #btn3');
	let para = document.getElementById('para1');

		document.addEventListener('submit', function submitMessage(e) {
			e.preventDefault();
			let p = document.createElement("p");
			p.textContent = "> " + message
			p.classList.add('pclass')
			container.appendChild(p);
			message = null
		});

	onMount(() => {
		const tl = gsap.timeline();
		const duration = 1;

	});


</script>
<main>
	<div class="shell__container">
		<div class="sb__container">
			<div class="round__container">
				<div class="round"></div>
				<div class="round"></div>
				<div class="round"></div>
			</div>
			<div class="shell__text" id="s__container" bind:this={container}>
				<p id="para1" class="pclass">> Bienvenue sur le Café des Devs :)</p>
				<p id="para2" class="pclass">> Le site est en maintenance . . .</p>
				<p id="para3" class="pclass">> Date d'ouverture : <span>Indisponible !</span></p>
			</div>
		</div>
		<div class="foot__container">
			<div class="sep__container">
				<div class="sep__shell"></div>
			</div>
			<form class="text__input" action="#">
				<p class="pclass">></p>
				<input class="inp__text pclass" placeholder="Insert text" bind:value={message}>
			</form>
		</div>
	</div>
	<div class="social__container">
		<button id="btn1" ><a href="https://discord.gg/2Ph7nNSQPJ"><img alt="" src="img/discord-brands.svg">DISCORD</a></button>
		<button id="btn2"><a href="https://www.instagram.com/cafedesdevs/"><img alt="" src="img/instagram-brands.svg">INSTAGRAM</a></button>
		<button id="btn3"><a href="https://github.com/cafe-des-devs"><img alt="" src="img/NoPath.svg">GITHUB</a></button>
	</div>
</main>
<style>

	* {
		padding: 0;
		margin: 0;

	}

	.social__container {
		display: flex;
		flex-direction: column;
		position: relative;
		right: 150px;
	}

	body {
		background-image: url("../public/img/bg.svg");
		width: 100%;

	}

	a {
		display: flex;
		justify-content: center;
		align-items: center;
		text-decoration: none;
		color: #16151D;
	}

	.sb__container {
		display: flex;
		flex-direction: column;
		align-content: space-between;

	}

	img {
		width: 45px;
		height: 45px;
		margin-right: 65px;
		margin-left: 15px;

	}

	.shell__container {
		background: #3E3D4B;
		border-radius: 15px;
		width: 80%;
		height: 620px;
		display: flex;
		flex-direction: column;
		max-width: 920px;
		justify-content: space-between;
		min-width: 245px;

	}

	button {
		display: flex;
		align-items: center;
		flex-direction: row;
		background-color: #C5C5C5;
		width: 290px;
		height: 60px;
		border: none;
		border-radius: 10px;
		font-family: "Segoe UI", serif;
		font-weight: bold;
		font-size: 1.5rem;
		margin-top: 20px;
		margin-bottom: 25px;

	}

	.text__input {
		display: flex;
		flex-direction: row;
		margin-left: 8px;

	}

	.inp__text:focus {


	}

	.sep__shell {
		height: 2px;
		width: 95%;
		background-color: #787878;

	}

	.sep__container {
		display: flex;
		justify-content: center;
		align-items: center;

	}

	.foot__container {
		margin-bottom: 20px;

	}

	.inp__text {
		margin-left: 10px;
		margin-top: 5px;
		opacity: 50%;
		width: 300px;
		background-color: #3E3D4B;
		border: none #787878;
		border-bottom-style: solid;
		font-size: 1.5rem;
		color: #FFFFFF;
	}

	.round__container {
		margin-top: 10px;
		margin-left: 10px;
		display: flex;
		flex-direction: row;
		justify-content: flex-start;
		align-items: center;
		margin-bottom: 10px;


	}

	.round:nth-child(1) {
		background-color: #DF5757;
	}

	.round:nth-child(2) {
		background-color: #FEBF2D;
	}

	.round:nth-child(3) {
		background-color: #27CC40;
	}

	:global(.pclass) {
		margin: 0 0 0 10px;
		font-size: 1.7rem;
		color: #FFFFFF;
		font-family: "Segoe UI", serif;

	}

	span {
		color: #DF5757;

	}

	.round {
		height: 20px;
		width: 20px;
		border-radius: 50%;
		background-color: red;
		margin: 5px;


	}

	main {
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	h1 {

	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

	@media (max-width: 1260px) {
		.social__container {
			flex-direction: row;
			position: static;

		}

		button {
			margin: 15px 10px 0;

		}

		main {
			flex-direction: column;

		}

	}

	@media (max-width: 925px) {
		.social__container {
			flex-direction: column;

		}

		button {
			margin-bottom: 0;

		}

	}

	@media (max-width: 475px) {
		.inp__text {
			width: 200px;

		}

		.shell__text, p {
			font-size: 1.2rem;

		}

		.pclass {
			font-size: 1.2rem;

		}

	}

</style>