<script>
	import {onMount} from "svelte";
  import {MDCList} from '@material/list';
  import {MDCRipple} from '@material/ripple';
  import Request from './Request.svelte'
  
  repos = data;
  
onMount(()=> {
  const list = new MDCList(document.querySelector('.mdc-list'));
  const listItemRipples = list.listElements.map((listItemEl) => new MDCRipple(listItemEl));
  });
</script>

<ul>
  {#if repos.length > 0}
		{#each repos as repo}
			<li>{repo.name}</li>
		{/each}
  {/if}  
</ul>

<!--
<ul class="mdc-list">
  <li class="mdc-list-item" tabindex="0">
    <span class="mdc-list-item__ripple"></span>
    <span class="mdc-list-item__text">Single-line item</span>
  </li>
  <li class="mdc-list-item">
    <span class="mdc-list-item__ripple"></span>
    <span class="mdc-list-item__text">Single-line item</span>
  </li>
  <li class="mdc-list-item">
    <span class="mdc-list-item__ripple"></span>
    <span class="mdc-list-item__text">Single-line item</span>
  </li>
</ul>
-->







