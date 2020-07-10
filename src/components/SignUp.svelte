<script>
    import { navigate } from "svelte-routing";
  import axios from "axios";
  let firstName;
  let secondName;
  let firstLastName;
  let secondLastName;
  let email;
  let phone;
  let district;
  let purchased;
  let message;
  let password;
  let color;
  const createUser = event => {
    const adminId = "5f065d34b89f6c5b54174eca";
    const body = {
      firstName,
      secondName,
      firstLastName,
      secondLastName,
      email,
      phone,
      district,
      purchased,
      adminId,
      password,
      role: "admin"
    };

    if (firstName && firstLastName && email && phone) {
      axios
        .post("http://localhost:5001/sign-up", body)
        .then(response => {
          showSnackbar("Usuario creado correctamente", "green");
            firstName = "";
            secondName = "";
            firstLastName = "";
            secondLastName = "";
            email = "";
            phone = "";
            district = "";
            purchased = "";
            password = "";
            setTimeout(() => {
                navigate("/Login", { replace: true }); 
            }, 3000)
        })
        .catch(error => {
          showSnackbar("Hubo un error al conectar con la base de datos", "red");
          console.error(error);
        });
    } else {
      showSnackbar("Por favor, completa los datos requeridos", "red");
    }
    event.preventDefault();
  };

  const showSnackbar = (text, color) => {
    message = text;
    var div = document.getElementById("snackbar");
    document.getElementById("snackbar").style.backgroundColor = color;
    var x = document.getElementById("snackbar");
    x.className = "show";
    setTimeout(function() {
      x.className = x.className.replace("show", "");
    }, 3000);
  };
</script>

<style>
  .snackbar-container {
    position: fixed;
    bottom: 0;
    left: 50%
  }
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
  button:active,
  button:hover {
    outline-width: 0;
  }
  button {
    background-color: white;
    color: black;
    border: 2px solid #3498db;
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
  *,
  *:before,
  *:after {
    box-sizing: inherit;
  }
</style>

<div class="snackbar-container">
  <div id="snackbar">{message}</div>
</div>

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
              <span class="col-md-1 col-md-offset-2 text-center">
                <i class="fa fa-user bigicon" />
              </span>
              <div class="col-md-8">
                <input
                  bind:value={firstName}
                  id="fname"
                  name="name"
                  type="text"
                  placeholder="First Name"
                  class="form-control"
                  required />
              </div>
            </div>
            <div class="form-group d-flex justify-content-center">
              <span class="col-md-1 col-md-offset-2 text-center">
                <i class="fa fa-user bigicon" />
              </span>
              <div class="col-md-8">
                <input
                  bind:value={secondName}
                  id="secondname"
                  name="name"
                  type="text"
                  placeholder="Second Name"
                  class="form-control" />
              </div>
            </div>
            <div class="form-group d-flex justify-content-center">
              <span class="col-md-1 col-md-offset-2 text-center">
                <i class="fa fa-user bigicon" />
              </span>
              <div class="col-md-8">
                <input
                  bind:value={firstLastName}
                  id="firstLastName"
                  name="name"
                  type="text"
                  placeholder="First Last Name"
                  class="form-control"
                  required />
              </div>
            </div>
            <div class="form-group d-flex justify-content-center">
              <span class="col-md-1 col-md-offset-2 text-center">
                <i class="fa fa-user bigicon" />
              </span>
              <div class="col-md-8">
                <input
                  bind:value={secondLastName}
                  id="secondLastName"
                  name="name"
                  type="text"
                  placeholder="Second Last Name"
                  class="form-control" />
              </div>
            </div>

            <div class="form-group d-flex justify-content-center">
              <span class="col-md-1 col-md-offset-2 text-center">
                <i class="fa fa-envelope-o bigicon" />
              </span>
              <div class="col-md-8">
                <input
                  bind:value={email}
                  id="email"
                  name="email"
                  type="text"
                  placeholder="Email Address"
                  class="form-control"
                  required />
              </div>
            </div>
            <div
              class="form-group d-flex justify-content-center"
              data-validate="Password is required">
              <span class="col-md-1 col-md-offset-2 text-center">
                <i class="fa fa-envelope-o bigicon" />
              </span>
              <div class="col-md-8">
                <input
                  bind:value={password}
                  id="password"
                  name="password"
                  type="password"
                  placeholder="Enter password"
                  class="form-control"
                  required
                  min="8" />
              </div>
            </div>
            <div class="form-group d-flex justify-content-center">
              <span class="col-md-1 col-md-offset-2 text-center">
                <i class="fa fa-phone-square bigicon" />
              </span>
              <div class="col-md-8">
                <input
                  bind:value={phone}
                  id="phone"
                  name="phone"
                  type="text"
                  placeholder="Phone"
                  class="form-control"
                  required/>
              </div>
            </div>
            <div class="form-group d-flex justify-content-center">
              <div class="col-md-4 text-center">
                <button on:click={createUser}>Submit</button>
              </div>
            </div>
          </fieldset>
        </form>
      </div>
    </div>
  </div>
</div>
