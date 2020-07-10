<script>
	import Tabs from '../shared/TabsGoups.svelte';
  let AP = ['Adorno Ortega Braulio Elias', 'Garcia Ortega Ruben Uriel', 'Montes Hernandez Gerardo Daniel','Aguayo González Jaime Francisco','Chávez Heredia Andrea '];
  let Group = ['HA', 'SO'];
  let activeitem = 'Adorno';
  let activeitemG = 'HA';
	const tabChange = (e) => {
		activeitemG = e.detail;
  } 
  const myFunction =()=>{
  var x = document.getElementById("myDIV");
  if (x.style.display === "none") {
    x.style.display = "block";
  } else {
    x.style.display = "none";
  }
}
const myFunction2 =()=>{
  var x = document.getElementById("myDIV2");
  if (x.style.display === "none") {
    x.style.display = "block";
  } else {
    x.style.display = "none";
  }
}
const myFunction3 =()=>{
  var x = document.getElementById("myDIV3");
  if (x.style.display === "none") {
    x.style.display = "block";
  } else {
    x.style.display = "none";
  }
}

</script>

<div class="container aligin-items-center">
    <div class="row">
        <div class="col-md-12">
            <div class="well well-sm">
                    <div class="d-flex justify-content-center">
                    <legend class="text-center header" id="View">Grups</legend>
                    </div>
            </div>
        </div>
    </div>
</div>
<div class="container d-flex justify-content-center">
     <div class="row">
          <Tabs {activeitemG} {Group} on:tabChange={tabChange}  />
  </div>
</div>
<style>
 #View {
	width: 100%;
	height: 30vh;
	background: url("/img/ViewU.jpg") center center;
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
  