<script>
  import axios from "axios";
  import { navigate } from "svelte-routing";
  import { IDuser } from "./store.js";
  import Home from "./Home.svelte";
  import Signup from "./components/SignUp.svelte";
  let email;
  let password;
  let message;
  let color;

  const setUserId = userId => {
    IDuser.set(userId);
  };
  const login = event => {
    const body = {
      email,
      password
    };
    event.preventDefault();
    axios
      .post("http://localhost:5001/login", body)
      .then(response => {
        console.log("%c⧭", "color: #408059", IDuser);
        console.log("%c⧭", "color: #ffcc00", response);
        const user = response.data.currentUser._id;
        IDuser.set(user);
        setTimeout(() => {
          navigate("/", { replace: false });
        }, 1000);
      })
      .catch(error => {
        event.preventDefault();
        showSnackbar("Hubo un error al hacer login", "red");
      });
  };

  const showSnackbar = (text, color) => {
    message = text;

    console.log("%c⧭", "color: #99adcc", "showNack");
    var div = document.getElementById("snackbar");
    document.getElementById("snackbar").style.backgroundColor = color;
    var x = document.getElementById("snackbar");
    x.className = "show";
    x.className = x.className.replace("show", "");
    setTimeout(function() {}, 3000);
  };
</script>

<style>
  .snackbar-container {
    position: fixed;
    bottom: 0;
    left: 60%;
  }
  #Log {
    width: 100%;
    height: 30vh;
    background: url("/img/bg-01.jpg") center center;
    background-size: cover;
    position: relative;
    margin-top: 70px;
    padding: 0;
  }
  .button:hover {
    background-color: #3498db;
    color: white;
  }
  button:hover,
  button:active,
  a:hover,
  a:active {
    color: #3498db;
  }
  button:active,
  button:hover,
  a:hover,
  a:active {
    outline-width: 0;
  }
  button,
  .button {
    background-color: white;
    color: black;
    border: 2px solid #3498db;
    padding: 10px 20px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin-left: 20px;
  }
  button,
  a {
    color: inherit;
  }
  button,
  a {
    background-color: transparent;
  }
  *,
  *:before,
  *:after {
    box-sizing: inherit;
  }

  /* input[type="password"] {
  color: transparent;
} */

  /*//////////////////////////////////////////////////////////////////
[ FONT ]*/

  /*  @font-face {
    font-family: Poppins-Regular;
    src: url("../fonts/poppins/Poppins-Regular.ttf");
  }

  @font-face {
    font-family: Poppins-Medium;
    src: url("../fonts/poppins/Poppins-Medium.ttf");
  }

  @font-face {
    font-family: Poppins-Bold;
    src: url("../fonts/poppins/Poppins-Bold.ttf");
  }

  @font-face {
    font-family: Poppins-SemiBold;
    src: url("../fonts/poppins/Poppins-SemiBold.ttf");
  }
 */
  /*//////////////////////////////////////////////////////////////////
[ RESTYLE TAG ]*/

  * {
    margin: 0px;
    padding: 0px;
    box-sizing: border-box;
  }

  body {
    height: 100%;
    font-family: Poppins-Regular, sans-serif;
  }

  /*---------------------------------------------*/
  a {
    font-family: Poppins-Regular;
    font-size: 14px;
    line-height: 1.7;
    color: #666666;
    margin: 0px;
    transition: all 0.4s;
    -webkit-transition: all 0.4s;
    -o-transition: all 0.4s;
    -moz-transition: all 0.4s;
  }

  a:focus {
    outline: none !important;
  }

  a:hover {
    text-decoration: none;
    color: #3498db;
  }

  /*---------------------------------------------*/

  /*---------------------------------------------*/

  /*//////////////////////////////////////////////////////////////////
[ Utility ]*/
  .txt1 {
    font-family: Poppins-Regular;
    font-size: 13px;
    line-height: 1.4;
    color: #999999;
  }

  /*//////////////////////////////////////////////////////////////////
[ login ]*/

  .limiter {
    width: 100%;
    margin: 0 auto;
  }

  .container-login100 {
    width: 100%;
    min-height: 100vh;
    display: -webkit-box;
    display: -webkit-flex;
    display: -moz-box;
    display: -ms-flexbox;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    padding: 15px;
    background: #ebeeef;
  }

  .wrap-login100 {
    width: 670px;
    background: #fff;
    border-radius: 10px;
    overflow: hidden;
    position: relative;
  }

  /*==================================================================
[ Title form ]*/
  .login100-form-title {
    width: 100%;
    position: relative;
    z-index: 1;
    display: -webkit-box;
    display: -webkit-flex;
    display: -moz-box;
    display: -ms-flexbox;
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    align-items: center;

    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;

    padding: 70px 15px 74px 15px;
  }

  .login100-form-title-1 {
    font-family: Poppins-Bold;
    font-size: 30px;
    color: #fff;
    text-transform: uppercase;
    line-height: 1.2;
    text-align: center;
  }

  .login100-form-title::before {
    content: "";
    display: block;
    position: absolute;
    z-index: -1;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    background-color: rgba(54, 84, 99, 0.7);
  }

  /*==================================================================
[ Form ]*/

  .login100-form {
    width: 100%;
    display: -webkit-box;
    display: -webkit-flex;
    display: -moz-box;
    display: -ms-flexbox;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    padding: 43px 88px 93px 190px;
  }

  /*------------------------------------------------------------------
[ Input ]*/

  .wrap-input100 {
    width: 100%;
    position: relative;
    border-bottom: 1px solid #b2b2b2;
  }

  .label-input100 {
    font-family: Poppins-Regular;
    font-size: 15px;
    color: #808080;
    line-height: 1.2;
    text-align: right;

    position: absolute;
    top: 14px;
    left: -105px;
    width: 80px;
  }

  /*---------------------------------------------*/
  .input100 {
    font-family: Poppins-Regular;
    font-size: 15px;
    color: #555555;
    line-height: 1.2;

    display: block;
    width: 100%;
    background: transparent;
    padding: 0 5px;
  }

  .focus-input100 {
    position: absolute;
    display: block;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    pointer-events: none;
  }

  .focus-input100::before {
    content: "";
    display: block;
    position: absolute;
    bottom: -1px;
    left: 0;
    width: 0;
    height: 1px;

    -webkit-transition: all 0.6s;
    -o-transition: all 0.6s;
    -moz-transition: all 0.6s;
    transition: all 0.6s;

    background: #3498db;
  }

  /*---------------------------------------------*/
  input.input100 {
    height: 45px;
  }

  .input100:focus + .focus-input100::before {
    width: 100%;
  }

  .has-val.input100 + .focus-input100::before {
    width: 100%;
  }

  /*==================================================================
[ Restyle Checkbox ]*/

  /*------------------------------------------------------------------
[ Button ]*/
  .container-login100-form-btn {
    width: 100%;
    display: -webkit-box;
    display: -webkit-flex;
    display: -moz-box;
    display: -ms-flexbox;
    display: flex;
    flex-wrap: wrap;
  }

  /*------------------------------------------------------------------
[ Responsive ]*/

  @media (max-width: 576px) {
    .login100-form {
      padding: 43px 15px 57px 117px;
    }
  }

  @media (max-width: 480px) {
    .login100-form {
      padding: 43px 15px 57px 15px;
    }

    .label-input100 {
      text-align: left;
      position: unset;
      top: unset;
      left: unset;
      width: 100%;
      padding: 0 5px;
    }
  }

  /*------------------------------------------------------------------
[ Alert validate ]*/

  .validate-input {
    position: relative;
  }
</style>

<div class="snackbar-container">
  <div id="snackbar">{message}</div>
</div>

<body>
  <div class="limiter">
    <div class="container-login100">
      <div class="wrap-login100">
        <div class="login100-form-title" id="Log">
          <br />
          <br />
          <span class="login100-form-title-1">Sign In</span>
        </div>

        <form class="login100-form validate-form">
          <div
            class="wrap-input100 validate-input m-b-26"
            data-validate="email is required">
            <span class="label-input100">Email</span>
            <input
              bind:value={email}
              class="input100"
              type="text"
              name="email"
              placeholder="Enter email"
              required />
            <span class="focus-input100" />
          </div>

          <div
            class="wrap-input100 validate-input m-b-18"
            data-validate="Password is required">
            <span class="label-input100">Password</span>
            <input
              bind:value={password}
              class="input100"
              type="password"
              name="pass"
              placeholder="Enter password"
              required />
            <span class="focus-input100" />
          </div>
          <div class=" container">
            <div class="flex-sb-m w-full p-b-30 row">
              <div>
                <a
                  href="$"
                  class="txt1 justify-content-center col-12 col-md-4 col-lg-6
                  d-flex justify-content-center">
                  Forgot Password?
                </a>
              </div>
            </div>
          </div>

          <div class="container-login100-form-btn justify-content-center">
            <div class="row">
              <div class="col-12 col-md-4 col-lg-6 ">
                <button on:click={login}>Login</button>

              </div>
              <div class="col-12 col-md-4 col-lg-6 ">
                <a
                  href="Signup"
                  class="btn btn-outline-primary button"
                  type="button"
                  style="width:100%;">
                  Sign up
                </a>
              </div>
            </div>
          </div>

        </form>
      </div>
    </div>
  </div>
</body>
