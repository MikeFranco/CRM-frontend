<style>
  /*header*/
  #header {
    height: 70px;
    transition: all 0.5s;
    z-index: 997;
    transition: all 0.5s;
    background: #fff;
    box-shadow: 0px 2px 15px rgba(0, 0, 0, 0.1);
  }

  #header .logo h1 {
    font-size: 28px;
    margin: 0;
    font-weight: 600;
    letter-spacing: 1px;
    text-transform: uppercase;
    color: #384046;
  }

  #header .logo h1 a,
  #header .logo h1 a:hover {
    color: #384046;
    text-decoration: none;
  }

  /*--------------------------------------------------------------
  # Header Social Links
  --------------------------------------------------------------*/
  .header-social-links a {
    color: #9ba6af;
    padding-left: 8px;
    display: inline-block;
    line-height: 1px;
    transition: 0.3s;
  }

  .header-social-links a:hover {
    color: #3498db;
  }

  @media (max-width: 768px) {
    .header-social-links {
      padding-right: 48px;
    }
    .header-social-links a {
      padding-left: 6px;
    }
  }
  /*Navi*/
  .nav-menu,
  .nav-menu * {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  .nav-menu > ul > li {
    position: relative;
    white-space: nowrap;
    float: left;
  }

  .nav-menu a {
    display: block;
    position: relative;
    color: #4f5a62;
    padding: 12px 15px;
    transition: 0.3s;
    font-size: 16px;
    font-weight: 500;
    font-family: "Poppins", sans-serif;
  }

  .nav-menu a:hover,
  .nav-menu .active > a,
  .nav-menu li:hover > a {
    color: #3498db;
    text-decoration: none;
  }

  .nav-menu .drop-down ul {
    display: block;
    position: absolute;
    left: 0;
    top: calc(100% + 30px);
    z-index: 99;
    opacity: 0;
    visibility: hidden;
    padding: 10px 0;
    background: #fff;
    box-shadow: 0px 0px 30px rgba(127, 137, 161, 0.25);
    transition: ease all 0.3s;
  }

  .nav-menu .drop-down:hover > ul {
    opacity: 1;
    top: 100%;
    visibility: visible;
  }

  .nav-menu .drop-down li {
    min-width: 180px;
    position: relative;
  }

  .nav-menu .drop-down ul a {
    padding: 10px 20px;
    font-size: 14px;
    text-transform: none;
    color: #21262a;
    font-weight: 400;
  }

  .nav-menu .drop-down ul a:hover,
  /* .nav-menu .drop-down ul .active > a, */
  .nav-menu .drop-down ul li:hover > a {
    color: #3498db;
  }

  .nav-menu .drop-down > a:after {
    content: "\ea99";
    font-family: IcoFont;
    padding-left: 5px;
  }

  .nav-menu .drop-down .drop-down ul {
    top: 0;
    left: calc(100% - 30px);
  }

  .nav-menu .drop-down .drop-down:hover > ul {
    opacity: 1;
    top: 0;
    left: 100%;
  }

  .nav-menu .drop-down .drop-down > a {
    padding-right: 35px;
  }

  .nav-menu .drop-down .drop-down > a:after {
    content: "\eaa0";
    font-family: IcoFont;
    position: absolute;
    right: 15px;
  }

  @media (max-width: 1366px) {
    .nav-menu .drop-down .drop-down ul {
      left: -90%;
    }
    .nav-menu .drop-down .drop-down:hover > ul {
      left: -100%;
    }
    .nav-menu .drop-down .drop-down > a:after {
      content: "\ea9d";
    }
  }
</style>

<header id="header" class="fixed-top d-flex align-items-center">

  <div class="container d-flex align-items-center m-5">

    <div class="logo mr-auto">
      <h1>
        <a href="index.html">BAGOMH</a>
      </h1>
    </div>

    <nav class="nav-menu d-none d-lg-block">
      <ul>
        <li class="active">
          <a href="#header">Inicio</a>
        </li>
        <li class="drop-down">
          <a href="#nada">Temas</a>
          <ul>
            <li>
              <a href="#about">About Us</a>
            </li>
            <li>
              <a href="#team">Team</a>
            </li>
          </ul>
        </li>
        <li>
          <a href="#services">Servicios</a>
        </li>
        <li>
          <a href="#portfolio">Introducción</a>
        </li>
        <li>
          <a href="#testimonials">Testimonials</a>
        </li>
        <li>
          <a href="#contact">Contacto</a>
        </li>

      </ul>
    </nav>
    <!-- .nav-menu -->

    <div class="header-social-links">
      <a href="https://www.facebook.com/ballos.ort" class="facebook">
        <i class="icofont-facebook" />
      </a>
      <a
        href="https://www.instagram.com/elias.06.05/?hl=es-la"
        class="instagram">
        <i class="icofont-instagram" />
      </a>
    </div>

  </div>

</header>
