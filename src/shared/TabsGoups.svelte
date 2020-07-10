<script>
import Tabs from './TabsVUser.svelte';
import { createEventDispatcher } from 'svelte';
const dispatch = createEventDispatcher();
let AP = ['Adorno Ortega Braulio Elias', 'Garcia Ortega Ruben Uriel', 'Montes Hernandez Gerardo Daniel','Aguayo González Jaime Francisco','Chávez Heredia Andrea '];
let activeitem = 'Adorno';

export let Group ;
export let activeitemG;
	const tabChange = (e) => {
		activeitem = e.detail;
  }
  const HA =()=>{
  var x = document.getElementById("HA");
  if (x.style.display === "none") {
    x.style.display = "block";
  } else {
    x.style.display = "none";
  }
}
const SO =()=>{
  var x = document.getElementById("SO");
  if (x.style.display === "none") {
    x.style.display = "block";
  } else {
    x.style.display = "none";
  }
}
</script>

<div class="tabs">

    <ul>
        {#each Group as group }
            
          <li on:click ={() => dispatch('tabChange', group)}>
                <div class:active={group === activeitemG} class="col-md-12"{group}>
                    
                    <div class="col-lg-4 col-md-4 d-flex align-items-stretch">
                        <div class="member">
                                <img src="assets/img/team/team-2.jpg" alt="">
                                <h4>{group}</h4>
                                <button class="btn btn-primary" on:click={() => HA()}>
                                    Details
                                </button>
                            <div class="collapse" id="{group}">
                                <div class="card card-body">
                                    <div class="social">
                                         <Tabs {activeitem} {AP} on:tabChange={tabChange}  />
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div> 
                </div>
            </li>
        {/each}    
    </ul>

</div>
<style>
ul li{
        list-style-type: none;
        position: relative;
        margin: 0px 16px;
        font-size: 18px;
        color:gray;
        cursor: pointer;
    }
</style>