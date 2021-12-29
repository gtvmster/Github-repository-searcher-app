<script>
   //Variaveis para receber o usuário e armazenar o respositório.
   let userName = ''
   let repos = []
     
   // Constante com função asincrona que fara o fetch na API do github,
   // e o await traz o resultado que são os repositórios do usuário.
   const getRepos = async (userName) => {
		if (userName) {
			const result = await fetch(`https://api.github.com/users/${userName}/repos`)
			repos = await result.json()
		}
	}
 </script>
 <!-- Campo que recebera o nome do usuário para a pesquisa-->
 <form on:submit|preventDefault={getRepos(userName)}>
 <input bind:value={userName} type="text" placeholder="Digite o usuário..">
 </form>

 <!--Lista de repositórios do usuário--> 
 <ul>
   {#if repos.length > 0}
      <!--Aqui usei o bloco each para, dentro do array armazenado na variavel repos,
      trazer apenas nome do reposotório do usuario.
      -->
      {#each repos as repo}
        <li>{repo.name}</li>
      {/each}
   {/if}
</ul>


