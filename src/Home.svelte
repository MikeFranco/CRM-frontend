<script>
	import Hero from './components/Hero.svelte';
	import Products from './components/DashProducts.svelte';
	import Delegaciones from './components/Dashdelegaciones.svelte';
	import Users from './components/Dashusers.svelte';
	import Tabs from './shared/Tabs.svelte';
	let AP = ['Adorno', 'Garcia', 'Montes'];
	let AM = ['Ortega', 'Ortega', 'Hernandez'];
	let PN = ['Braulio', 'Ruben', 'Gerardo'];
	let SN = ['Elias', 'Uriel', 'Daniel'];
	let activeitem = 'Adorno';
	const tabChange = (e) => {
		activeitem = e.detail;
	} 

</script>
<Hero />
<section >
<div id="container">
	<div class="row total">
		<div class="col-md-6 user d-flex justify-content-center ">
			<button href="#usuaerio">lola </button>  
		</div>
		<div class="col-md-6 group d-flex justify-content-center ">
			<button href="#grupo">lola </button> 
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
.button:hover {
    background-color: #3498db;
    color: white;
  }
  button:hover,
  button:active,
  a:hover,
  a:active {
    color: #3498db;
  }
  button:active,
  button:hover,
  a:hover,
  a:active {
    outline-width: 0;
  }
  button,
  .button {
    background-color: white;
    color: black;
    border: 2px solid #3498db;
    padding: 30% 30%;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
	margin-left: 20px;
	margin-bottom: 55%;
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