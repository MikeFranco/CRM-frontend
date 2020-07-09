<script>
import Usern from './charts/Newusers.svelte';
import Userc from './charts/user.svelte';

let datan=[90,19];
let datac=[70,49];
let t= " ya estoy hasta la puta madre";
let colr="purple";
const myFunctio =()=> {
	 let t;
	 var div = document.getElementById( 'snackbar' );
	document.getElementById("snackbar").style.backgroundColor=colr;
  var x = document.getElementById("snackbar");
  x.className = "show";  
  setTimeout(function(){ x.className = x.className.replace("show", ""); }, 3000);
}
</script>

<br>
<br>
<br>
<div class="form-group d-flex justify-content-center">
                            <div class="col-md-6 text-center">  
                             
                           <button on:click={() => myFunctio()}>Submit</button>   
                            <div id="snackbar">{t}
							</div>
                            
                            </div>
							
	</div>
<div class="container">
		<div class="row">
			 	<div id="clientes" class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
          			<article class="card" style="width: 100%; height: 100%;">
                		<div class="card-body">
							<h5 class="card-title">Client</h5>
							<br><br><br><br><br>
							   <article class="card" style="width: 100%;height:18%;background: #FF6384;">
                					<div class="card-body">
										<h5 class="card-title">Registered</h5>
											<h5>{datan[0]}</h5>			
            						</div>
          						</article> 
								 
								<article class="card" style="width: 100%;height:18%;background: #36A2EB;">
                					<div class="card-body">
										<h5 class="card-title">New</h5>
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
							<h5 class="card-title">Consumers</h5>
							<br><br><br><br><br>
							   <article class="card" style="width: 100%;height:18%;background: #FF6384;">
                					<div class="card-body">
										<h5 class="card-title">Active</h5>
											<h5>{datac[0]}</h5>			
            						</div>
          						</article>   
								<article class="card" style="width: 100%;height:18%;background: #36A2EB;">
                					<div class="card-body">
										<h5 class="card-title">Inactive</h5>
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
	
	
<style>
#snackbar {
  visibility: hidden; /* Hidden by default. Visible on click */
  min-width: 250px; /* Set a default minimum width */
  margin-left: -125px; /* Divide value of min-width by 2 */
  background-color: #333; /* Black background color */
  color: #fff; /* White text color */
  text-align: center; /* Centered text */
  border-radius: 2px; /* Rounded borders */
  padding: 16px; /* Padding */
  position: top; /* Sit on top of the screen */
  z-index: 1; /* Add a z-index if needed */
  left: 50%; /* Center the snackbar */
  bottom: 30px; /* 30px from the bottom */
}

/* Show the snackbar when clicking on a button (class added with JavaScript) */
#snackbar.show {
  visibility: visible; /* Show the snackbar */
  /* Add animation: Take 0.5 seconds to fade in and out the snackbar.
  However, delay the fade out process for 2.5 seconds */
  -webkit-animation: fadein 0.5s, fadeout 0.5s 2.5s;
  animation: fadein 0.5s, fadeout 0.5s 2.5s;
}

/* Animations to fade the snackbar in and out */
@-webkit-keyframes fadein {
  from {bottom: 0; opacity: 0;}
  to {bottom: 30px; opacity: 1;}
}

@keyframes fadein {
  from {bottom: 0; opacity: 0;}
  to {bottom: 30px; opacity: 1;}
}

@-webkit-keyframes fadeout {
  from {bottom: 30px; opacity: 1;}
  to {bottom: 0; opacity: 0;}
}

@keyframes fadeout {
  from {bottom: 30px; opacity: 1;}
  to {bottom: 0; opacity: 0;}
}
</style>