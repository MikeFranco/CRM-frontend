<script>
  import { createEventDispatcher, onMount } from "svelte";
  import axios from "axios";
  const dispatch = createEventDispatcher();
  const back = "http://localhost:5001";
  let showTable = false;
  let groups = [
    {
      firstName: "Mike",
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
  const getGroups = () => {
    const adminId = "5f07a503656fe87849dfa85a";
    axios
      .get(`${back}/groups?adminId=${adminId}`)
      .then(response => {
        groups = response.data.getGroupsById;
        showTable = true;
      })
      .catch(error => console.error(error));
  };
  const editGroup = group => {
    console.log('Me faltó ésto :(');
  }
  const deleteGroup = id => {
    axios
      .delete(`${back}/groups?id=${id}`)
      .then(response => {
        alert("Borrado correctamente");
      })
      .catch(error => console.error(error));
  };
  onMount(getGroups);
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
    font-size: 50px;
  }
  #muestra {
    margin-top: 15vh;
  }
</style>

<fieldset>
  <div class="d-flex justify-content-center">
    <legend class="text-center header" id="Reg">Groups</legend>
  </div>
</fieldset>
{#if showTable}
  <table id="muestra" class="table">
    <thead class="thead-dark">
      <tr>
        <th>Group Name</th>
        <th>Users inside</th>
        <th>Edit</th>
        <th>Delete</th>
      </tr>
    </thead>
    <tbody>
      {#each groups as group}
        <tr>
          <td>
            <p>{group.name}</p>
          </td>
          <td>
            <p>{group.users.length}</p>
          </td>
          <td>
            <input
              alt="users"
              type="image"
              src="/img/edit.png"
              width="45"
              height="45"
              on:click={() => editGroup(group)} />
          </td>
          <td>
            <input
              alt="groups"
              type="image"
              src="/img/drop.png"
              width="45"
              height="45"
              on:click={() => deleteGroup(group._id)} />
          </td>
        </tr>
      {/each}

    </tbody>
  </table>
{/if}
