<script lang="ts">
  import Router, { link } from "svelte-spa-router";
  import { wrap } from "svelte-spa-router/wrap";
  //import About from "./pages/About.svelte";
  //import Error404 from "./pages/Error404.svelte";

  const routes = {
    "/": wrap({
      asyncComponent: () => import("./pages/Home.svelte"),
    }),
    "/about": wrap({
      asyncComponent: () => import("./pages/About.svelte"),
    }),
    "*": wrap({
      asyncComponent: () => import("./pages/Error404.svelte"),
    }),
  };
</script>

<main>
  <ul>
    <li>
      <a href="/" use:link>Home</a>
    </li>
    <li>
      <a href="/about" use:link>About</a>
    </li>
    <li>
      <a href="/404" use:link>Error</a>
    </li>
  </ul>
  <Router {routes} />
</main>
