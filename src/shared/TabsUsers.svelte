<script>
import { createEventDispatcher } from 'svelte';
const dispatch = createEventDispatcher();
export let AP ;
</script>

  <table id='muestra'>
   <thead>
<tr><th>User</th><th>District</th><th>Email</th><th>Delete</th>
</thead>
  <tbody>
   
        {#each AP as ap }
        
                    <tr><td><textarea> {ap}</textarea>
                    </td><td> <select name="transporte"  id="lista" >
                                <option value ="">--Select a option--</option>
                                <option value ="Álvaro Obregón">Álvaro Obregón</option>
                                <option value ="Azcapotzalco">Azcapotzalco</option>
                                <option value ="Benito Juárez">Benito Juárez</option>
                                <option value ="Coyoacán">Coyoacán</option>
                                <option value ="Cuajimalpa">Cuajimalpa</option>
                                <option value ="Cuauhtémoc">Cuauhtémoc</option>
                                <option value ="Gustavo A. Madero">Gustavo A. Madero</option>
                                <option value ="Iztacalco">Iztacalco</option>
                                <option value ="Iztapalapa">Iztapalapa</option>
                                <option value ="Magdalena Contreras">Magdalena Contreras</option>
                                <option value ="Miguel Hidalgo">Miguel Hidalgo</option>
                                <option value ="Milpa Alta">Milpa Alta</option>
                                <option value ="Tláhuac">Tláhuac</option>
                                <option value ="Tlalpan">Tlalpan</option>
                                <option value ="Venustiano Carranza">Venustiano Carranza</option>
                                <option value ="Xochimilco">Xochimilco</option>
                                </select> 
                    </td> <td> <textarea> {ap}</textarea></td><td> <input type=image src="/img/drop.png"width="45"height="45" onclick="eliminar()"></td></tr>  
        {/each}  
       
    
 </tbody></table>  
<style>

  
  
      
</style>