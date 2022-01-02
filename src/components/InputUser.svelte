<script>
    import Request from './Request.svelte'
    let userName
     

</script>

<!-- Campo que recebera o nome do usuário para a pesquisa-->
<Request let:getRepos>
<form on:submit|preventDefault={getRepos(userName)}>
<input bind:value={userName} type="text" placeholder="Digite o usuário..">
</form> 
</Request>
