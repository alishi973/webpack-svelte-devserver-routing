<script>
  import { onMount } from "svelte";
  import { Route, useNavigate } from "svelte-navigator";
  import { user } from "../../store/main.store";

  export let component, path;

  const navigate = useNavigate();

  onMount(() => {
    if (!$user.loggedIn) {
      navigate("/login");
    }
  });
</script>

{#if $user?.loggedIn}
  <Route {path} {component} />
{/if}
