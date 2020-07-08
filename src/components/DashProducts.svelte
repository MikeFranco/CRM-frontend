<script>
import Chart from './charts/Products.svelte';
let data=[30,19,19,70];
</script>
<br>
<br>
<br>
<div class="container">
		<div class="row">
			 	<div id="clientes" class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
          			<article class="card" style="width: 100%; height: 100%;">
                		<div class="card-body">
							<h5 class="card-title">Productos comprados</h5>
							   <article class="card" style="width: 100%;height:18%;background: #FF6384;">
                					<div class="card-body">
										<h5 class="card-title">Cojines</h5>
											<h5>{data[0]} uds</h5>			
            						</div>
          						</article>   
								<article class="card" style="width: 100%;height:18%;background: #36A2EB;">
                					<div class="card-body">
										<h5 class="card-title">Almohadas</h5>
											<h5>{data[1]} uds</h5>			
            						</div>
          						</article>  
								<article class="card" style="width: 100%;height:18%;background: #FFCE56;">
                					<div class="card-body">
										<h5 class="card-title">Camas</h5>
											<h5>{data[2]} uds</h5>			
            						</div>
          						</article>
								<article class="card" style="width: 100%;height:18%;background: #9966FF;">
                					<div class="card-body">
										<h5 class="card-title">Colchones</h5>
											<h5>{data[3]} uds</h5>			
            						</div>
          						</article>
								      				
            			</div>
          			</article>
        		</div>	
			 	<div id="DashCliente" class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
          			<article class="card" style="width: 100%;">
                		<div class="card-body">
						 <Chart {data}/>   
            			</div>
          			</article>
        		</div>
		</div>
	</div>