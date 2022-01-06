<script>
    import { useNavigate, useLocation } from "svelte-navigator";
    import { user } from "../stores"
  
    const navigate = useNavigate();
    const location = useLocation();
  
    let username;
    let password;
  
    function handleSubmit() {
      $user = { username, password };
      const from = ($location.state && $location.state.from) || "/";
      navigate(from, { replace: true });
    }
  </script>
  
  <div class="bg-blue-300 px-2 py-3">
    <form on:submit={handleSubmit} class="p-2">
      <h1>Login page</h1>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam libero nulla, blandit in placerat in, dictum in massa. Morbi dignissim neque lacus, sit amet pulvinar augue fermentum at. Etiam pellentesque imperdiet mi sed dapibus. Etiam luctus augue enim, sed gravida magna dictum sed. Fusce non eros justo.</p>
      <input
          class="my-2 rounded-md p-1"
          bind:value={username}
          type="text"
          name="username"
          placeholder="Username"
      />
      <br />
      <input
          class="my-2 rounded-md p-1"
          bind:value={password}
          type="password"
          name="password"
          placeholder="Password"
      />
      <br />
      <button class="btn btn-sm btn-primary rounded-md my-2" type="submit">Login</button>
    </form>
  </div>
  