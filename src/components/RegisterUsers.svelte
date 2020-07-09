<div class="container aligin-items-center">
    <div class="row">
        <div class="col-md-12">
            <div class="well well-sm">
                <form class="form-horizontal " method="post">
                    <fieldset>
                    <div>
                    <legend class="text-center header" id="Reg">Create User</legend>
                    </div>
                        <div class="form-group d-flex justify-content-center">
                            <span class="col-md-1 col-md-offset-2 text-center"><i class="fa fa-user bigicon"></i></span>
                            <div class="col-md-8">
                                <input id="fname" name="name" type="text" placeholder="First Name" class="form-control">
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
                                <input id="firstLastName" name="name" type="text" placeholder="First Last Name" class="form-control">
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
                                <input id="email" name="email" type="text" placeholder="Email Address" class="form-control">
                            </div>
                        </div>
                        <div class="form-group d-flex justify-content-center" >
                            <span class="col-md-1 col-md-offset-2 text-center"><i class="fa fa-envelope-o bigicon"></i></span>
                            <div class="col-md-8">
                                <p>District:             <select name="transporte"  id="lista" >
                                <option value ="">--Select a option--</option>
                                <option value ="Álvaro Obregón">Álvaro Obregón</option>
                                <option value ="Azcapotzalco">Azcapotzalco</option>
                                <option value ="Benito Juárez">Benito Juárez</option>
                                <option value ="Coyoacán">Coyoacán</option>
                                <option value ="Cuajimalpa">Cuajimalpa</option>
                                <option value ="Cuauhtémoc">Cuauhtémoc</option>
                                <option value ="Gustavo A. Madero">Gustavo A. Madero</option>
                                <option value ="Iztacalco">Iztacalco</option>
                                <option value ="Iztapalapa">Iztapalapa</option>
                                <option value ="Magdalena Contreras">Magdalena Contreras</option>
                                <option value ="Miguel Hidalgo">Miguel Hidalgo</option>
                                <option value ="Milpa Alta">Milpa Alta</option>
                                <option value ="Tláhuac">Tláhuac</option>
                                <option value ="Tlalpan">Tlalpan</option>
                                <option value ="Venustiano Carranza">Venustiano Carranza</option>
                                <option value ="Xochimilco">Xochimilco</option>
                                </select> 
                            </div>
                        </div>
                        <div class="form-group d-flex justify-content-center">
                            <span class="col-md-1 col-md-offset-2 text-center"><i class="fa fa-phone-square bigicon"></i></span>
                            <div class="col-md-8">
                                <input id="phone" name="phone" type="text" placeholder="Phone" class="form-control">
                            </div>
                        </div>
                        <div class="form-group d-flex justify-content-center">
                            <div class="col-md-6 text-center">
                            <a href="/" class="btn btn-outline-primary button" type="button" style="width:100%;">Submit</a>                            </div>
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
	background: url("/img/Register.jpg") center center;
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