<script>
	import Header from './Components/Header.svelte';
	import Hero from './Components/Hero.svelte';
</script>
<Header />
<Hero />
<main id="main">
 <section id="what-we-do" class="what-we-do">
      <div class="container mt-5">

        <div class="section-title">
          <h2>BAGOMH</h2>
          <p>Es una herramienta para aquellos quienes quieran adentrarse al mundo de la programación. </p>
        </div>

        <div class="row">

          <div class="col-lg-4 col-md-6 d-flex align-items-stretch">
          	<div class="card" style="width: 18rem;">
  <div class="card-body">
  	  <div class="icon-box">
              <div class="icon"><i class="bx bxl-dribbble"></i></div>
               <div class="bg-primary text-light">
					Interactiva
				</div>
  	  <p class="card-text">Contamos con un programa interactivo para un mejor aprendizaje.</p>

          
            </div>
          </div>

        <div class="col-lg-4 col-md-6 d-flex align-items-stretch mt-4 mt-md-0">
          	<div class="card" style="width: 18rem;">
  				<div class="card-body">
            		<div class="icon-box">
             	 <div class="icon"><i class="bx bx-file" ></i></div>
             	 <div class="bg-primary text-light">
					Recordar
				</div>
               <p class="card-text">No volverás a copiar y pegar con estos cursos.</p>
            		</div>
          </div>
            	</div>
		</div>


          <div class="col-lg-4 col-md-6 d-flex align-items-stretch mt-4 mt-lg-0">
           <div class="card" style="width: 18rem;">
  				<div class="card-body">
            		<div class="icon-box">
             	 <div class="icon"><i class="bx bx-tachometer" ></i></div>
             	  <div class="bg-primary text-light">
					Ágil
				</div>
               <p class="card-text">Desde el primer momento conocerás todo aquello en lo que deberás enfocarte.</p>
            		</div>
          </div>
            	</div>
		</div>
          </div>

        </div>

    

</main>

<style>

	main {

		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	
	}
	
</style>