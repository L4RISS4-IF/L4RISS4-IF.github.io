<script>
	import { projetos, áreas } from '$lib/projetos.js';

	let áreasSelecionadas = $state([]);
	let filtrados = $state(projetos.slice());

	function filtrarÁrea(event) {
		console.log('testando');
		if (event.target.checked) {
			áreasSelecionadas.push(event.target.value);
		} else {
			áreasSelecionadas.splice(áreasSelecionadas.indexOf(event.target.value), 1);
		}

		if (áreasSelecionadas.length == 0) {
			filtrados = projetos.slice();
		} else {
			filtrados = [];
			for (const projeto of projetos) {
				for (const área of áreasSelecionadas) {
					if (projeto.áreas.includes(área)) {
						filtrados.push(projeto);
						break;
					}
				}
			}
		}
	}

	function participarProjeto(projeto) {
		alert('Agora você está participando do projeto!');
	}
</script>

<div class="alinharcentro">
	<h1>Projetos em Andamento...</h1>
</div>

<br />

<div class="row align-items-center mb-3">
	{#each áreas as área}
		<div class="col">
			<div class="form-check form-check-inline">
				<input
					type="checkbox"
					oninput={filtrarÁrea}
					class="form-check-input"
					id={área}
					value={área}
				/>
				<label class="form-check-label" for={área}>{área}</label>
			</div>
		</div>
	{/each}
</div>

<div class="row g-4">
	{#each filtrados as projeto}
		<div class="col-md-6 col-xl-3">
			<div class="card h-100">
				<div class="row g-0">
					<div class="col-3 col-sm-4">
						<img src={projeto.imagem} class="img-fluid rounded-start" alt="imagem do projeto" />
					</div>
					<div class="col-sm-8">
						<div class="card-body">
							<h5 class="card-title">{projeto.título}</h5>
							<h6 class="card-subtitle mb-2 text-body-secondary">{projeto.status}</h6>
							<p class="card-text">{projeto.descrição}</p>
							<p class="card-text">
								{#each projeto.áreas as área}
									<span class="badge text-bg-secondary mx-1">{área}</span>
								{/each}
							</p>
							<button class="btn btn-primary" onclick={() => participarProjeto(projeto)}>Participar</button>
						</div>
					</div>
				</div>
			</div>
		</div>
	{/each}
</div>

<div class="row m-3">
	<div class="col">
		<div class="alinharcentro">
			<a href="/Termos e Condições">
				<button>Anterior</button>
			</a>
		</div>
	</div>
</div>

<style>
	h1 {
		color: rgb(80, 180, 220);
	}

	.alinharcentro {
		text-align: center;
	}
</style>
