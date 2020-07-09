<script>
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
<div class="container aligin-items-center">
    <div class="row">
        <div class="col-md-12">
            <div class="well well-sm">
                <form class="form-horizontal " method="post">
                    <fieldset>
                    <div class="d-flex justify-content-center">
                    <legend class="text-center header" id="Reg">Sign Up</legend>
                    </div>
                        <div class="form-group d-flex justify-content-center">
                            <span class="col-md-1 col-md-offset-2 text-center"><i class="fa fa-user bigicon"></i></span>
                            <div class="col-md-8">
                                <input id="fname" name="name" type="text" placeholder="First Name" class="form-control" required>
                            </div>
                        </div>
                        <div class="form-group d-flex justify-content-center">
                            <span class="col-md-1 col-md-offset-2 text-center"><i class="fa fa-user bigicon"></i></span>
                            <div class="col-md-8">
                                <input id="secondname" name="name" type="text" placeholder="Second Name" class="form-control">
                            </div>
                        </div>
                        <div class="form-group d-flex justify-content-center">
                            <span class="col-md-1 col-md-offset-2 text-center"><i class="fa fa-user bigicon"></i></span>
                            <div class="col-md-8">
                                <input id="firstLastName" name="name" type="text" placeholder="First Last Name" class="form-control" required>
                            </div>
                        </div>
                        <div class="form-group d-flex justify-content-center">
                            <span class="col-md-1 col-md-offset-2 text-center"><i class="fa fa-user bigicon"></i></span>
                            <div class="col-md-8">
                                <input id="secondLastName" name="name" type="text" placeholder="Second Last Name" class="form-control">
                            </div>
                        </div>

                        <div class="form-group d-flex justify-content-center">
                            <span class="col-md-1 col-md-offset-2 text-center"><i class="fa fa-envelope-o bigicon"></i></span>
                            <div class="col-md-8">
                                <input id="email" name="email" type="text" placeholder="Email Address" class="form-control" required>
                            </div>
                        </div>
                        <div class="form-group d-flex justify-content-center" data-validate = "Password is required">
                            <span class="col-md-1 col-md-offset-2 text-center"><i class="fa fa-envelope-o bigicon"></i></span>
                            <div class="col-md-8">
                                <input id="password" name="password" type="password" placeholder="Enter password" class="form-control" required min="8">
                            </div>
                        </div>
                        <div class="form-group d-flex justify-content-center">
                            <span class="col-md-1 col-md-offset-2 text-center"><i class="fa fa-phone-square bigicon"></i></span>
                            <div class="col-md-8">
                                <input id="phone" name="phone" type="text" placeholder="Phone" class="form-control">
                            </div>
                        </div>
                        <div class="form-group d-flex justify-content-center">
                            <div class="col-md-4 text-center">
                            <button  on:click={() => myFunctio()}>Submit</button>   
                                <div id="snackbar">{t}
                                </div>      
                        </div>
                        </div>
                    </fieldset>
                </form>
            </div>
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
input:invalid {
  border: 2px solid red;
}

input:valid {
  border: 2px solid gray;
}
button:hover {
    background-color: #3498db;
    color: white;
}
button:active, button:hover {
    outline-width: 0;
}
button{
    background-color: white;
    color: black;
    border: 2px solid  #3498db;
    padding: 10px 20px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin-left: 20px;
}
button {
    color: inherit;
}
button {
    background-color: transparent;
}
*, *:before, *:after {
    box-sizing: inherit;
}
</style>