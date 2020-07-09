<script>
	import Tabs from '../shared/TabsUsers.svelte';
    let AP = ['Adorno Ortega Braulio Elias', 'Garcia Ortega Ruben Uriel', 'Montes Hernandez Gerardo Daniel','Aguayo González Jaime Francisco','Chávez Heredia Andrea '];
	let activeitem = 'Adorno';
	const tabChange = (e) => {
		activeitem = e.detail;
	} 

</script>
<div class="container aligin-items-center">
    <div class="row">
        <div class="col-md-12">
            <div class="well well-sm">
                <form class="form-horizontal " method="post">
                    <fieldset>
                    <div class="d-flex justify-content-center">
                    <legend class="text-center header" id="Reg">Edit User</legend>
                    </div>  
                    </fieldset>
                </form>
            </div>
        </div>
    </div>
    <div class="container d-flex justify-content-center">
     <div class="row">
        
         <Tabs {activeitem} {AP} on:tabChange={tabChange}  />
       
     </div>
    
    </div>
              
</div>
<style>
  #Reg {
	width: 100%;
	height: 30vh;
	background: url("/img/welcom.jpg") center center;
	background-size: cover;
	position: relative;
	margin-top: 70px;
	padding: 0;
  }
  .header {
   margin: 0 0 10px 0;
	font-size: 48px;
	font-weight: 700;
	line-height: 56px;
	color: #fff;
}

</style>