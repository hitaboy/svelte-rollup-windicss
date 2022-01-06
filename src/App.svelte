<script>
  import { Router, Route, Link } from "svelte-navigator";
  import PrivateRoute from "./PrivateRoute.svelte";
  import Profile from './components/Profile.svelte';
  import Login from './components/Login.svelte';
  import Home from './components/Home.svelte';
  import About from './components/About.svelte';
</script>

<svelte:head>
  <title>Svelte + Rollup + Windicss</title>
</svelte:head>

<Router>
  <header class="p-2">
    <nav>
      <Link to="/">Home</Link>
      <Link to="about">About</Link>
      <Link to="profile">Profile</Link>
    </nav>
  </header>

  <main>
    <Route path="login" component="{Login}" />
    <Route path="/" component="{Home}" />
    <Route path="about" component="{About}" />
    <PrivateRoute path="profile" let:location let:registerFocus>
      <Profile />
    </PrivateRoute>
  </main>
</Router>
