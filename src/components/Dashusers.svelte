<script>
  import Usern from "./charts/Newusers.svelte";
  import Userc from "./charts/user.svelte";
  import { onMount } from "svelte";
  import axios from "axios";
  let datan = [90, 19];
  let datac;
  let labelsConsumersData;
  let showChart = false;

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
        labelsConsumersData = Object.keys(consumersData);
        datac = Object.values(consumersData);
        showChart = true;
      })
      .catch(error => {
        console.error(error);
      });
  };
  onMount(userConsumers);
</script>

<br />
<br />
<br />
{#if showChart}
  <div class="container">
    <div class="row">
      <div
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
                <h5>{datan[0]}</h5>
              </div>
            </article>

            <article
              class="card"
              style="width: 100%;height:18%;background: #36A2EB;">
              <div class="card-body">
                <h5 class="card-title">New</h5>
                <h5>{datan[1]}</h5>
              </div>
            </article>
          </div>
        </article>
      </div>
      <div
        id="DashCliente"
        class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
        <article class="card" style="width: 100%;">
          <div class="card-body">
            <Usern {datan} />
          </div>
        </article>
      </div>
    </div>
  </div>
  <div class="container">
    <div class="row">
      <div
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
                <h5>{datac[1]}</h5>
              </div>
            </article>
            <article
              class="card"
              style="width: 100%;height:18%;background: #FF6384;">
              <div class="card-body">
                <h5 class="card-title">Inactive</h5>
                <h5>{datac[0]}</h5>
              </div>
            </article>
          </div>
        </article>
      </div>
      <div
        id="DashCliente"
        class="col-12 col-md-4 col-lg-6 d-flex justify-content-center">
        <article class="card" style="width: 100%;">
          <div class="card-body">
            <Userc {datac} labels={labelsConsumersData}/>
          </div>
        </article>
      </div>
    </div>
  </div>
{/if}
