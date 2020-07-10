<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let AP;
  export let activeitem;
</script>

<style>
  .tabs {
    margin-bottom: 40px;
  }

  ul li {
    list-style-type: none;
    position: relative;
    margin: 0px 16px;
    font-size: 18px;
    color: gray;
    cursor: pointer;
  }
  ul li:last-child {
    border-bottom: none;
  }

  ul li label {
    font-size: 18px;
  }
  ul li label input {
    opacity: 0;
  }
  ul li label .check {
    position: absolute;
    top: 10%;
    left: -10px;
    width: 20px;
    height: 20px;
    display: block;
    background: #000;
    box-sizing: border-box;
    border-radius: 4px;
  }
  ul li label .check:before {
    content: "";
    position: absolute;
    top: 3px;
    left: 3px;
    right: 3px;
    bottom: 3px;
    background: #000b10;
    border-radius: 2px;
    transition: 0.5s;
    transform: translateX(400px);
  }

  ul li label input:checked ~ .check:before {
    background: #adff00;
    box-shadow: 0 0 15px #adff00;
    transform: translateX(0px);
  }
</style>

<div class="tabs">
  <ul>
    {#each AP as ap}
      <li on:click={() => dispatch('tabChange', ap)}>
        <div class:active={ap === activeitem} class="col-md-12" {ap}>
          <label>
            {ap}
            <input type="checkbox" name={ap} />
            <span class=" check" />
          </label>
        </div>
      </li>
    {/each}
  </ul>

</div>
