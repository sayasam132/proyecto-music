<script>
	import { Router, Route, Link } from "svelte-routing";
	import Login from './login.svelte';
	import Windows from './windows.svelte';
	import Caja from './caja.svelte';
  	import Ingresarcuenta from "./ingresarcuenta.svelte";

  </script>
  
  <div>
	<Router>
	  <nav>
		<Link to="/">Login</Link>
		<Link to="/Ingresarcuenta">Ingresarcuenta</Link>
		<Link to="/windows">Windows</Link>
		<Link to="/caja">Caja</Link>

	  </nav>
  
	  <Route path="/" component={Login} />
	  <Route path="/Ingresarcuenta" component={Ingresarcuenta} />
	  <Route path="/windows" component={Windows} />
	  <Route path="/caja" component={Caja} />

	</Router>
  </div>
  
  <style>
	nav {
	  margin-bottom: 20px;
	}
  </style>
  