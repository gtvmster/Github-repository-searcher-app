<script>
	import {onMount} from "svelte";
  import {MDCList} from '@material/list';
  import {MDCRipple} from '@material/ripple';
  import { data } from './Store.svelte'
  import Request from './Request.svelte'
  
  $: repos = $data;
  
onMount(()=> {
  const list = new MDCList(document.querySelector('.mdc-list'));
  const listItemRipples = list.listElements.map((listItemEl) => new MDCRipple(listItemEl));
  });
</script>

<ul class="mdc-list">
  {#if repos}
		{#each repos as repo}
    <li class="mdc-list-item" tabindex="0">
      <span class="mdc-list-item__ripple"></span>
      <span class="mdc-list-item__text">{repo.name}</span>
    </li>
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







