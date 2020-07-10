<script>
import { createEventDispatcher } from 'svelte';
const dispatch = createEventDispatcher();
export let User;
</script>

  <table id='muestra' class="table">
   <thead class="thead-dark">
<tr><th>User</th><th>District</th><th>Email</th><th>Delete</th><th>Edit</th>
</thead>
  <tbody>
   
        {#each User as user }
        
                    <tr><td><p id={user.firstName}{ user.secondName}{ user.firstLastName}{user.secondLastName}>{user.firstName}{ user.secondName}{ user.firstLastName}{user.secondLastName}</p>
                    </td><td> <p id={user.district}>{user.district}</p> 
                    </td> <td> <p id={user.email}>{user.email}</p></td><td> <input alt="users" type=image src="/img/drop.png"width="45"height="45" onclick="eliminar()"></td>
                    <td> <input alt="users" type=image src="/img/edit.png"width="45"height="45" onclick="eliminar()"id></td></tr>  
        {/each}  
       
    
 </tbody></table>  
<style>
      
</style>