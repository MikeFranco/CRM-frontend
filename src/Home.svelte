<script>
  import { IDuser } from "./store.js";
  import Hero from "./components/Hero.svelte";
  import Products from "./components/DashProducts.svelte";
  import Delegaciones from "./components/Dashdelegaciones.svelte";
  import Users from "./components/Dashusers.svelte";
  import Tabs from "./shared/Tabs.svelte";
  const tabChange = e => {
    activeitem = e.detail;
	};
	let userId;
	IDuser.subscribe(value => {
		userId = value;
	})
</script>


<Hero />
<section >
<div id="container">
	<div class="row total">
		<div class="col-md-6 user d-flex justify-content-center ">
			<button href="#usuaerio">Users </button>  
		</div>
		<div class="col-md-6 group d-flex justify-content-center ">
			<button href="#grupo">Groups </button> 
		</div>
		
</div>
</section>
<!--> <Tabs {activeitem} {items} on:tabChange={tabChange}  />
{#if activeitem === 'Usuarios' }
<Users />
{:else if activeitem === 'Delegacion'}
<Delegaciones />
{:else if activeitem === 'Productos'}
<Products />
{/if}
-->

<style>

  button:hover,
  button:active{
    color: #fff;
    background-color: 3498db;

  }
  button:active,
  button:hover{
    outline-width: 0;
  }
  button
  {
    background-color: white;
    color: black;
    border: 2px solid #3498db;
    padding: 20% 30%;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 80px;
    margin-left: 20px;
    margin-bottom: 30%;
    cursor: pointer;
  }
  button,
  a {
    color: inherit;
  }
  button,
  a {
    background-color: transparent;
  }
  *,
  *:before,
  *:after {
    box-sizing: inherit;
  }

#container{
	padding: 0;
	margin: 0px;
}
.user {
	padding: 0;
	width: 50%;
	margin: 0px;
	padding: 0px;
    

}
.group {
	width: 50%;
	height: 70%;
	margin: 0px;
	padding: 0px;

}
	
</style>
