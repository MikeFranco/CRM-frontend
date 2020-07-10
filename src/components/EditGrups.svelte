<script>
	import Tabs from '../shared/TabsVUser.svelte';
    let AP = ['Adorno Ortega Braulio Elias', 'Garcia Ortega Ruben Uriel', 'Montes Hernandez Gerardo Daniel','Aguayo González Jaime Francisco','Chávez Heredia Andrea '];
	let activeitem = 'Adorno';
	const tabChange = (e) => {
		activeitem = e.detail;
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

<div class="container d-flex justify-content-center">
     <div class="row">
          <div class="col-lg-4 col-md-4 d-flex align-items-stretch">
            <div class="member">
              <img src="assets/img/team/team-2.jpg" alt="">
              <h4>HA </h4>
               <button class="btn btn-primary" on:click={() => myFunction()}>
                   Details
              </button>
              <div class="collapse" id="myDIV">
                <div class="card card-body">
                  <div class="social">
                      <Tabs {activeitem} {AP} on:tabChange={tabChange}  />
                      </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-lg-4 col-md-4 d-flex align-items-stretch">
            <div class="member">
              <img src="assets/img/team/team-2.jpg" alt="">
              <h4>SO</h4>
               <button class="btn btn-primary" on:click={() => myFunction2()}>
                   Details
              </button>
              <div class="collapse" id="myDIV2">
                <div class="card card-body">
                  <div class="social">
                      <Tabs {activeitem} {AP} on:tabChange={tabChange}  />
                      </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-lg-4 col-md-4 d-flex align-items-stretch">
            <div class="member">
              <img src="assets/img/team/team-3.jpg" alt="">
              <h4>PLA</h4>
            <button class="btn btn-primary" on:click={() => myFunction3()}>
                Details
            </button>
              <div class="collapse" id="myDIV3">
                <div class="card card-body">
                  <div class="social">
                      <Tabs {activeitem} {AP} on:tabChange={tabChange}  />
                      </div>
                </div>
              </div>
            </div>
          </div>

        </div>
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
  