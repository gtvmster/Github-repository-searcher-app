<script>
    import {onMount} from "svelte";
    import {MDCTopAppBar} from '@material/top-app-bar';
    import InputUser from './InputUser.svelte'
 

    onMount(() => {
        const topAppBarElement = document.querySelector('.mdc-top-app-bar');
        const topAppBar = new MDCTopAppBar(topAppBarElement);
    })
</script>

<header class="mdc-top-app-bar">
    <div class="mdc-top-app-bar__row">
      <section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-start">
        <span class="mdc-top-app-bar__title">Github repository searcher - Fiança Fácil</span>
      </section>
      <section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-end" role="toolbar">
            <InputUser/> 
      </section>
    </div>
  </header>
  <main class="mdc-top-app-bar--fixed-adjust">
    
  </main>
