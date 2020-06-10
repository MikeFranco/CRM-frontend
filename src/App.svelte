<script>
	export let name;
</script>

<main>
<header id="header" class="fixed-top d-flex align-items-center">

    <div class="container d-flex align-items-center m-5">

      <div class="logo mr-auto">
        <h1><a href="index.html">BAGOMH</a></h1>
        <!-- Uncomment below if you prefer to use an image logo -->
        <!-- <a href="index.html"><img src="assets/img/logo.png" alt="" class="img-fluid"></a>-->
      </div>

      <nav class="nav-menu d-none d-lg-block">
        <ul>
          <li class="active"><a href="#header">Inicio</a></li>
          <li class="drop-down"><a href="#nada">Temas</a>
            <ul>
              <li><a href="#about">About Us</a></li>
              <li><a href="#team">Team</a></li>             
            </ul>
          </li>
          <li><a href="#services">Servicios</a></li>
          <li><a href="#portfolio">Introducción</a></li>
          <li><a href="#testimonials">Testimonials</a></li>
          <li><a href="#contact">Contacto</a></li>

        </ul>
      </nav><!-- .nav-menu -->

      <div class="header-social-links">
        <a href="https://www.facebook.com/ballos.ort" class="facebook"><i class="icofont-facebook"></i></a>
        <a href="https://www.instagram.com/elias.06.05/?hl=es-la" class="instagram"><i class="icofont-instagram"></i></a>
      </div>

    </div>
  </header>

	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>