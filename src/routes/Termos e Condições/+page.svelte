<script>
    let aceitar = false;
</script>

<div class="alinharcentro">
    <h1>Termos e Condições</h1>

    <h2>1. Aceitação dos Termos</h2>
    <p>Ao acessar nosso site, você concorda com esses Termos e nossa Política de Privacidade.</p>
    
    <h2>2. Uso dos Serviços</h2>
    <p>Os serviços disponíveis não podem ser utilizados de maneira ilegal ou prejudicial.</p>
    
    <h2>3. Conta de Usuário</h2>
    <p>Você é responsável por manter suas informações atualizadas e seguras.</p>
    
    <h2>4. Propriedade</h2>
    <p>O conteúdo do nosso site é de nossa propriedade e não pode ser usado sem autorização.</p>
    
    <h2>5. Limitação de Responsabilidade</h2>
    <p>Não nos responsabilizamos por danos decorrentes do uso dos nossos serviços.</p>
    
    <h2>6. Privacidade</h2>
    <p>Suas informações são tratadas de acordo com nossa Política de Privacidade.</p>
    
    <h2>7. Mudanças nos Termos</h2>
    <p>Podemos alterar esses Termos a qualquer momento.</p>

    <h2>8. Encerramento da Conta</h2>
    <p>Podemos suspender ou encerrar sua conta se você violar estes Termos.</p>
    
    <h2>9. Legislação</h2>
    <p>Esses Termos são regidos pelas leis do país.</p>
    
    <h2>10. Contato</h2>
    <p>Se tiver dúvidas, entre em contato com a nossa equipe de suporte.</p>
    
    <h2>
        <label>
            <input type="checkbox" bind:checked={aceitar} />
            Eu aceito os Termos e Condições.
        </label>
    </h2>
    
    <a href="/">
        <button>Anterior</button>
    </a>

    <a href="/Projetos">
        <button disabled={!aceitar}>Próximo</button>
    </a>
</div>

<style>
	h1 {
		color: rgb(80, 180, 220);
	}

	h2 {
		color: rgb(125, 200, 235);
	}

	p {
		color: rgb(150, 215, 240);
		font-size: 1.5rem;
	}

	.alinharcentro{
		text-align: center;
	}
</style>