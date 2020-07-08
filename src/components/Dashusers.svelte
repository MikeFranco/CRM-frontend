<script>
import Usern from './charts/Newusers.svelte';
import Userc from './charts/user.svelte';

let datan=[90,19];
let datac=[70,49];
</script>
<br>
<br>
<br>
<div class="container">
		<div class="row">
			 	<div id="clientes" class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
          			<article class="card" style="width: 100%; height: 100%;">
                		<div class="card-body">
							<h5 class="card-title">Clientes</h5>
							<br><br><br><br><br>
							   <article class="card" style="width: 100%;height:18%;background: #FF6384;">
                					<div class="card-body">
										<h5 class="card-title">Registrados</h5>
											<h5>{datan[0]}</h5>			
            						</div>
          						</article> 
								 
								<article class="card" style="width: 100%;height:18%;background: #36A2EB;">
                					<div class="card-body">
										<h5 class="card-title">Nuevos</h5>
											<h5>{datan[1]}</h5>			
            						</div>
          						</article>     				
            			</div>
          			</article>
        		</div>	
			 	<div id="DashCliente" class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
          			<article class="card" style="width: 100%;">
                		<div class="card-body">
						 <Usern {datan}/>   
            			</div>
          			</article>
        		</div>
		</div>
	</div>
	<div class="container">
		<div class="row">
			 	<div id="clientes" class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
          			<article class="card" style="width: 100%; height: 100%;">
                		<div class="card-body">
							<h5 class="card-title">Consumidores</h5>
							<br><br><br><br><br>
							   <article class="card" style="width: 100%;height:18%;background: #FF6384;">
                					<div class="card-body">
										<h5 class="card-title">Activos</h5>
											<h5>{datac[0]}</h5>			
            						</div>
          						</article>   
								<article class="card" style="width: 100%;height:18%;background: #36A2EB;">
                					<div class="card-body">
										<h5 class="card-title">Inactivos</h5>
											<h5>{datac[1]}</h5>			
            						</div>
          						</article>       				
            			</div>
          			</article>
        		</div>	
			 	<div id="DashCliente" class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
          			<article class="card" style="width: 100%;">
                		<div class="card-body">
						 <Userc {datac}/>   
            			</div>
          			</article>
        		</div>
		</div>
	</div>
	
	