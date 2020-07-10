<script>
  import Usern from "./charts/Newusers.svelte";
  import Userc from "./charts/user.svelte";
  import { onMount } from "svelte";
  import axios from "axios";
  let datan;
  let datac;
  let labelsConsumersData;
  let labelsClients;
  let showChart = false;
  let message;
  let color;

  const userConsumers = () => {
    const adminId = "5f065d34b89f6c5b54174eca";
    axios
      .get(`http://localhost:5001/users?adminId=${adminId}`)
      .then(response => {
        const users = response.data.getUsersByAdminId;
        const consumersData = users.reduce((carry, user, index, self) => {
          const key = user.bought ? "Active" : "Inactive";
          const keyLength = self.filter(value => value.bought == user.bought)
            .length;
          carry[key] = keyLength;
          return carry;
        }, {});
        const totalUsers = users.length;
        const today = new Date();
        const yesterday = new Date();
        yesterday.setDate(yesterday.getDate() - 1);
        const newRegisters = users.filter(
          item =>
            new Date(item.createdAt) <= today &&
            new Date(item.createdAt) >= yesterday
        ).length;
        const clients = {
          Registered: newRegisters,
          New: totalUsers
        };
        labelsConsumersData = Object.keys(consumersData);
        datac = Object.values(consumersData);
        labelsClients = Object.keys(clients);
        datan = Object.values(clients);
        showChart = true;
      })
      .catch(error => {
        showSnackbar("Hubo un error al conectar con la base de datos", "red");
        console.error(error);
      });
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
  onMount(userConsumers);
</script>

<style>
  .container {
    margin-top: 20vh;
  }
  .snackbar-container {
    margin-top: 7vh;
  }
</style>

<div class="snackbar-container">
  <div id="snackbar">{message}</div>
</div>

{#if showChart}
  <div class="container">
    <div class="row">
      <!-- <div
        id="clientes"
        class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
        <article class="card" style="width: 100%; height: 100%;">
          <div class="card-body">
            <h5 class="card-title">Client</h5>
            <br />
            <br />
            <br />
            <br />
            <br />
            <article
              class="card"
              style="width: 100%;height:18%;background: #FF6384;">
              <div class="card-body">
                <h5 class="card-title">Registered</h5>
                <h5>{datan[0] ? datan[0] : 0}</h5>
              </div>
            </article>

            <article
              class="card"
              style="width: 100%;height:18%;background: #36A2EB;">
              <div class="card-body">
                <h5 class="card-title">New</h5>
                <h5>{datan[1] ? datan[1] : 0}</h5>
              </div>
            </article>
          </div>
        </article>
      </div> -->
      <div
        id="DashCliente"
        class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
        <article class="card" style="width: 100%;">
          <div class="card-body">
            <h5 class="card-title">Clients</h5>
            <Usern {datan} labels={labelsClients} />
          </div>
        </article>
      </div>
      <div
        id="DashCliente"
        class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
        <article class="card" style="width: 100%;">
          <div class="card-body">
            <h5 class="card-title">Consumers</h5>
            <Userc {datac} labels={labelsConsumersData} />
          </div>
        </article>
      </div>
    </div>
  </div>
  <div class="container">
    <div class="row">
      <!--  <div
        id="clientes"
        class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
        <article class="card" style="width: 100%; height: 100%;">
          <div class="card-body">
            <h5 class="card-title">Consumers</h5>
            <br />
            <br />
            <br />
            <br />
            <br />
            <article
              class="card"
              style="width: 100%;height:18%;background: #36A2EB;">
              <div class="card-body">
                <h5 class="card-title">Active</h5>
                <h5>{datac[1] ? datac[1] : 0}</h5>
              </div>
            </article>
            <article
              class="card"
              style="width: 100%;height:18%;background: #FF6384;">
              <div class="card-body">
                <h5 class="card-title">Inactive</h5>
                <h5>{datac[0] ? datac[0] : 0}</h5>
              </div>
            </article>
          </div>
        </article>
      </div> -->
    </div>
  </div>
{/if}
