<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let AP;
  export let activeitem;
</script>

<style>
  ul li {
    list-style-type: none;
    position: relative;
    margin: 0px 16px;
    font-size: 18px;
    cursor: pointer;
    border: 2px red;
  }
</style>

<div class="tabs">

  <ul>
    {#each AP as ap}
      <li on:click={() => dispatch('tabChange', ap)}>
        <div class:active={ap === activeitem} class="col-md-12" {ap}>{ap}</div>
      </li>
    {/each}
  </ul>

</div>
