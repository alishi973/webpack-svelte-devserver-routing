<script>
  import { Router, Route, Link } from "svelte-navigator";
  import PrivateRoute from "../component/router/PrivateRoute.svelte";
  import Home from "./Home";
  import NotFound from "./404";
  import Login from "./Login";
  import Register from "./Register";
</script>

<Router primary={false}>
  <Link to="/">Go to home</Link>
  <Link to="/register">Go to register</Link>
  <PrivateRoute path="/" component={Home} />
  <Route path="/login" component={Login} />
  <Route path="/register" component={Register} />
  <Route path="*" component={NotFound} />
</Router>
