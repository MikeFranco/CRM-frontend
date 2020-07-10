<script>
  import Tabs from "../shared/TabsUsers.svelte";
  let User = [
    {
      firstName: "Mike",
      secondName: "Angel",
      firstLastName: "Franco",
      secondLastName: "",
      email: "unemail3@gmail.com",
      password: "123456",
      phone: "5544221133",
      district: "Benito Juárez",
      bought: "yes",
      purchased: "cama",
      role: "admin"
    },

    {
      firstName: "Mike",
      secondName: "Angel",
      firstLastName: "Franco",
      secondLastName: "",
      email: "unemail3@gmail.com",
      password: "123456",
      phone: "5544221133",
      district: "Benito Juárez",
      bought: "yes",
      purchased: "cama",
      role: "admin"
    },

    {
      firstName: "Mike",
      secondName: "Angel",
      firstLastName: "Franco",
      secondLastName: "",
      email: "unemail3@gmail.com",
      password: "123456",
      phone: "5544221133",
      district: "Benito Juárez",
      bought: "yes",
      purchased: "cama",
      role: "admin"
    }
  ];
  let AP = [
    "Adorno Ortega Braulio Elias",
    "Garcia Ortega Ruben Uriel",
    "Montes Hernandez Gerardo Daniel",
    "Aguayo González Jaime Francisco",
    "Chávez Heredia Andrea "
  ];
  let activeitem = "Adorno";
  const tabChange = e => {
    activeitem = e.detail;
  };
  let t = " ya estoy hasta la puta madre";
  let colr = "purple";
  const myFunctio = () => {
    let t;
    var div = document.getElementById("snackbar");
    document.getElementById("snackbar").style.backgroundColor = colr;
    var x = document.getElementById("snackbar");
    x.className = "show";
    setTimeout(function() {
      x.className = x.className.replace("show", "");
    }, 3000);
  };
</script>

<style>
  #Reg {
    width: 100%;
    height: 30vh;
    background: url("/img/Edit.jpg") center center;
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

      <Tabs {activeitem} {User} on:tabChange={tabChange} />

    </div>

  </div>

</div>
<div class="form-group d-flex justify-content-center">
  <div class="col-md-6 text-center">
    <button on:click={() => myFunctio()}>Submit</button>
    <div id="snackbar">{t}</div>
  </div>
</div>
