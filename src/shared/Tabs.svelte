<script>
import { createEventDispatcher } from 'svelte';
const dispatch = createEventDispatcher();
export let items;
export let activeitem;
</script>

<div class="tabs">
    <ul>
        {#each items as item}
          <li on:click ={() => dispatch('tabChange', item)}>
                <div class:active={item === activeitem}>
                    {item}
                </div>
            </li>
        {/each}    
    </ul>

</div>
<style>
    .tabs{
        margin-bottom: 40px;

    }
    ul{
        display: flex;
        justify-content: center;
        padding: 0px;
        list-style-type: none;
            }
    li{
        margin: 0px 16px;
        font-size: 28px;
        color:gray;
        cursor: pointer;
    }
    .active{
        color: #3498db;
        border-bottom: 2px solid #3498db;
        padding-bottom: 8px;
    }
</style>