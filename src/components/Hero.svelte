<section id="hero" class=" d-flex flex-column justify-content-center align-items-center">
<p>
</p>
    <div class="container text-center text-md-left" data-aos="fade-up">
      <h1>Bienvenido a <span>MPBA</span></h1>
      <h2>Somos un equipo</h2>
      <p></p>
    </div>
  </section>
  <style> 
  		/*--------------------------------------------------------------
  # Hero
  --------------------------------------------------------------*/
  #hero {
	width: 100%;
	height: 30%;
	background: url("/img/hero-bg.jpg") center center;
	background-size: cover;
	position: relative;
	margin-top: 70px;
	padding: 0;
  }
  
  #hero:before {
	content: "";
	background: rgba(56, 64, 70, 0.7);
	position: absolute;
	bottom: 0;
	top: 0;
	left: 0;
	right: 0;
  }
  
  #hero .container {
	z-index: 2;
  }
  
  #hero h1 {
	margin: 0 0 10px 0;
	font-size: 48px;
	font-weight: 700;
	line-height: 56px;
	color: #fff;
  }
  
  #hero h1 span {
	border-bottom: 4px solid #3498db;
  }
  
  #hero h2 {
	color: rgba(255, 255, 255, 0.8);
	margin-bottom: 30px;
	font-size: 24px;
  }
  
  @media (max-width: 768px) {
	#hero h1 {
	  font-size: 30px;
	  line-height: 36px;
	}
	#hero h2 {
	  font-size: 18px;
	  line-height: 24px;
	  margin-bottom: 30px;
	}
  }
  </style>