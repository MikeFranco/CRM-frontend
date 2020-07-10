<script>
import { createEventDispatcher } from 'svelte';
const dispatch = createEventDispatcher();
export let User;
</script>

  <table id='muestra' class="table">
   <thead class="thead-dark">
<tr><th>User</th><th>District</th><th>Email</th><th>Delete</th>
</thead>
  <tbody>
   
        {#each User as user }
        
                    <tr><td><p>{user.firstName}{ user.secondName}{ user.firstLastName}{user.secondLastName}</p>
                    </td><td> <p>{user.district}</p> 
                    </td> <td> <p> {user.email}</p></td><td> <input alt="users" type=image src="/img/drop.png"width="45"height="45" onclick="eliminar()"></td></tr>  
        {/each}  
       
    
 </tbody></table>  
<style>
      
</style>