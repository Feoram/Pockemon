<script>
  import Tailwind from "./Tailwind.svelte";
  import {Link, Route, Router} from "svelte-routing";
  import Home from "./lib/routes/Home.svelte";
</script>

<Tailwind />

<Router>
    <Route path="/" component={Home} />
</Router>