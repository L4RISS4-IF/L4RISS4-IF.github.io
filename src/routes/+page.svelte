<script>
	let nome = '';
	let idade = 0;
	let acesso = false;
	let salvo = false;

	function verificar() {
		if (idade >= 18 && nome != "") {
			acesso = true;
		} else {
			acesso = false;
		}
	}

	function salvar() {
		alert('Dados salvos com sucesso!');
		salvo = true;
	}
</script>

<div class="alinharcentro">
	<h1>Bem-vindo à nossa empresa!</h1>
	<h2>Vamos começar...</h2>

	<p>Digite o seu nome:</p>
	<input type="text" bind:value={nome} oninput={verificar} placeholder="Digite o seu nome..." />

	<p>Digite a sua idade:</p>
	<input type="number" min="0" bind:value={idade} oninput={verificar} />

	{#if idade < 18}
		<p>Desculpe, você não pode utilizar o site.</p>
	{:else}
		<p>Acesso liberado!</p>
		<button onclick={salvar} disabled={!acesso}>Salvar</button>
	{/if}

	{#if salvo}
		<a href="/Termos e Condições">
			<button>Próximo</button>
		</a>
	{/if}
</div>

<style>
	h1 {
		color: rgb(80, 180, 220);
	}

	h2 {
		color: rgb(125, 200, 235);
        font-size: 2.0rem;
	}

	p {
		color: rgb(150, 215, 240);
		font-size: 1.5rem;
	}

	.alinharcentro{
		text-align: center;
	}
</style>