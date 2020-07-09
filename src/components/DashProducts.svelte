<script>
  import Products from "./charts/Products.svelte";
  import { onMount } from "svelte";
  import axios from "axios";
  let data;
  let labels;
  let message;
  let color;
  let showChart = false;

  const getChartInfo = () => {
    const adminId = "5f065d34b89f6c5b54174eca";
    axios
      .get(`http://localhost:5001/users?adminId=${adminId}`)
      .then(response => {
        const users = response.data.getUsersByAdminId;
        const productsData = users.reduce((carry, user, index, self) => {
          const key = user.purchased ? user.purchased : "dont";
          if (key != "dont") {
            const keyLength = self.filter(value => value.purchased == key)
              .length;
            carry[key] = keyLength;
          }
          return carry;
        }, {});
        labels = Object.keys(productsData);
        console.log("%c⧭", "color: #cc0088", productsData);
        data = Object.values(productsData);
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
  onMount(getChartInfo);
</script>

<style>
  .container {
    margin-top: 15vh;
  }
  .snackbar-container {
    margin-top: 7vh;
  }
</style>

<div class="snackbar-container">
  <div id="snackbar">{message}</div>
</div>
<div class="container">
  <div class="row">
    <!-- <div
      id="clientes"
      class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
      <article class="card" style="width: 100%; height: 100%;">
        <div class="card-body">
          <h5 class="card-title">Products purchased</h5>
          <article
            class="card"
            style="width: 100%;height:18%;background: #FF6384;">
            <div class="card-body">
              <h5 class="card-title">Cojines</h5>
              <h5>{data[0]} uds</h5>
            </div>
          </article>
          <article
            class="card"
            style="width: 100%;height:18%;background: #36A2EB;">
            <div class="card-body">
              <h5 class="card-title">Almohadas</h5>
              <h5>{data[1]} uds</h5>
            </div>
          </article>
          <article
            class="card"
            style="width: 100%;height:18%;background: #FFCE56;">
            <div class="card-body">
              <h5 class="card-title">Camas</h5>
              <h5>{data[2]} uds</h5>
            </div>
          </article>
          <article
            class="card"
            style="width: 100%;height:18%;background: #9966FF;">
            <div class="card-body">
              <h5 class="card-title">Colchones</h5>
              <h5>{data[3]} uds</h5>
            </div>
          </article>

        </div>
      </article>
    </div> -->
    {#if showChart}
      <div
        id="DashCliente"
        class="col-12 col-md-12 col-lg-6 d-flex justify-content-center">
        <article class="card" style="width: 100%;">
          <div class="card-body">
            <h5 class="card-title">Products purchased</h5>
            <Products {data} {labels} />
          </div>
        </article>
      </div>
    {/if}
  </div>
</div>
