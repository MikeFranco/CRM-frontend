
<div class="container aligin-items-center">
    <div class="row">
        <div class="col-md-12">
            <div class="well well-sm">
                <form class="form-horizontal " method="post">
                    <fieldset>
                    <div>
                    <legend class="text-center header" id="Reg">Register User</legend>
                    </div>
                        <div class="form-group d-flex justify-content-center">
                            <span class="col-md-1 col-md-offset-2 text-center"><i class="fa fa-user bigicon"></i></span>
                            <div class="col-md-8">
                                <input id="fname" name="name" type="text" placeholder="Name" class="form-control">
                            </div>
                        </div>
                        <div class="form-group d-flex justify-content-center">
                            <span class="col-md-1 col-md-offset-2 text-center"><i class="fa fa-user bigicon"></i></span>
                            <div class="col-md-8">
                                <input id="lname" name="name" type="text" placeholder="Last Name" class="form-control">
                            </div>
                        </div>

                        <div class="form-group d-flex justify-content-center">
                            <span class="col-md-1 col-md-offset-2 text-center"><i class="fa fa-envelope-o bigicon"></i></span>
                            <div class="col-md-8">
                                <input id="email" name="email" type="text" placeholder="Email Address" class="form-control">
                            </div>
                        </div>

                        <div class="form-group d-flex justify-content-center">
                            <span class="col-md-1 col-md-offset-2 text-center"><i class="fa fa-phone-square bigicon"></i></span>
                            <div class="col-md-8">
                                <input id="phone" name="phone" type="text" placeholder="Phone" class="form-control">
                            </div>
                        </div>
                        <div class="form-group d-flex justify-content-center">
                            <div class="col-md-12 text-center">
                                <button type="submit" class="btn btn-primary btn-lg">Submit</button>
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