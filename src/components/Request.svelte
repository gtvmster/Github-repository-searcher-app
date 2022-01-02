<script>
	import { data } from './Store.svelte'
	let userName = ''
   	let repos = [];
 
   	const getRepos = async (userName) => {
	if (userName) {
			const result = await fetch(`https://api.github.com/users/${userName}/repos`)
			data = await result.json();
			console.log(data);

		}
	}
 </script>

<slot {getRepos}/>


  
 
 





