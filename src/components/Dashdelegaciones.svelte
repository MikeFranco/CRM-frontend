<script>
  import Delegacion from "./charts/Delegacion.svelte";
  import axios from "axios";
  import { onMount } from "svelte";
  let data;
  let labels;
  let showChart = false;
  let message;
  let color;

  const getChartInfo = () => {
    const adminId = "5f065d34b89f6c5b54174eca";
    axios
      .get(`http://localhost:5001/users?adminId=${adminId}`)
      .then(response => {
        const users = response.data.getUsersByAdminId;
        const districtData = users.reduce((carry, user, index, self) => {
          const key = user.district;
          const keyLength = self.filter(value => value.district == key).length;
          carry[key] = keyLength;
          return carry;
        }, {});
        labels = Object.keys(districtData);
        data = Object.values(districtData);
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
    margin-top: 20vh;
  }
 .snackbar-container {
    margin-top: 7vh;
  }
</style>

<div class="snackbar-container">
  <div id="snackbar">{message}</div>
</div>

<div class="container">
  <div class="row justify-content-center">
    <div
      id="DashCliente"
      class="col-12 col-md-12 col-lg-6 d-flex justify-content-center">
      <article class="card" style="width: 100%;">
        <div class="card-body">
          <h5 class="card-title">Usuarios por Alcaldias</h5>
          {#if showChart}
            <Delegacion {data} {labels} />
          {/if}
        </div>
      </article>
    </div>
  </div>
  <!--  <div class="row">
    <div
      id="delegaciones"
      class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
      <article class="card" style="width: 100%; height: 100%;">
        <div class="card-body">
          <h5 class="card-title">Usuarios por Alcaldias</h5>
          <article
            class="card"
            style="width: 100%;height:12%;background: #FFFFFF;">
            <div class="card-body">
              <h5 class="card-title">Álvaro Obregón</h5>
              <h5>{data[0]}</h5>
            </div>
          </article>
          <article
            class="card"
            style="width: 100%;height:12%;background: #C0C0C0;">
            <div class="card-body">
              <h5 class="card-title">Azcapotzalco</h5>
              <h5>{data[1]}</h5>
            </div>
          </article>
          <article
            class="card"
            style="width: 100%;height:12%;background: #808080;">
            <div class="card-body">
              <h5 class="card-title">Benito Juárez</h5>
              <h5>{data[2]}</h5>
            </div>
          </article>
          <article
            class="card"
            style="color:white; width: 100%;height:12%;background: #000000;">
            <div class="card-body">
              <h5 class="card-title">Coyoacán</h5>
              <h5>{data[3]}</h5>
            </div>
          </article>
          <article
            class="card"
            style="color:white; width: 100%;height:12%;background: #FF0000;">
            <div class="card-body">
              <h5 class="card-title">Cuajimalpa de Morelos</h5>
              <h5>{data[4]}</h5>
            </div>
          </article>
          <article
            class="card"
            style=" color:white; width: 100%;height:12%;background: #800000;">
            <div class="card-body">
              <h5 class="card-title">Cuauhtémoc</h5>
              <h5>{data[5]}</h5>
            </div>
          </article>
          <article
            class="card"
            style=" width: 100%;height:12%;background: #FFFF00;">
            <div class="card-body">
              <h5 class="card-title">Gustavo A. Madero</h5>
              <h5>{data[6]}</h5>
            </div>
          </article>
          <article
            class="card"
            style="width: 100%;height:12%;background: #808000;">
            <div class="card-body">
              <h5 class="card-title">Iztacalco</h5>
              <h5>{data[7]}</h5>
            </div>
          </article>
        </div>
      </article>
    </div>
    <div
      id="delegaciones"
      class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
      <article class="card" style="width: 100%; height: 100%;">
        <div class="card-body">
          <h5 class="card-title">Usuarios por Alcaldias</h5>
          <article
            class="card"
            style="width: 100%;height:12%;background: #00FF00 ;">
            <div class="card-body">
              <h5 class="card-title">Iztapalapa</h5>
              <h5>{data[8]}</h5>
            </div>
          </article>
          <article
            class="card"
            style="color:white; width: 100%;height:12%;background: #008000;">
            <div class="card-body">
              <h5 class="card-title">Magdalena Contreras</h5>
              <h5>{data[9]}</h5>
            </div>
          </article>
          <article
            class="card"
            style="width: 100%;height:12%;background: #00FFFF;">
            <div class="card-body">
              <h5 class="card-title">Miguel Hidalgo</h5>
              <h5>{data[10]}</h5>
            </div>
          </article>
          <article
            class="card"
            style="color:white; width: 100%;height:12%;background: #008080;">
            <div class="card-body">
              <h5 class="card-title">Milpa Alta</h5>
              <h5>{data[11]}</h5>
            </div>
          </article>
          <article
            class="card"
            style="color:white; width: 100%;height:12%;background: #0000FF;">
            <div class="card-body">
              <h5 class="card-title">Tláhuac</h5>
              <h5>{data[12]}</h5>
            </div>
          </article>
          <article
            class="card"
            style="color:white; width: 100%;height:12%;background: #000080;">
            <div class="card-body">
              <h5 class="card-title">Tlalpan</h5>
              <h5>{data[13]}</h5>
            </div>
          </article>
          <article
            class="card"
            style="width: 100%;height:12%;background: #FF00FF;">
            <div class="card-body">
              <h5 class="card-title">Venustiano Carranza</h5>
              <h5>{data[14]}</h5>
            </div>
          </article>
          <article
            class="card"
            style="color:white; width: 100%;height:12%;background: #800080 ;">
            <div class="card-body">
              <h5 class="card-title">Xochimilco</h5>
              <h5>{data[15]}</h5>
            </div>
          </article>
        </div>
      </article>
    </div>

  </div> -->
</div>
