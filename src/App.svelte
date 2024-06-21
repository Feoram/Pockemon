<script>
  import First from "./lib/routes/First.svelte";
  import Two from "./lib/routes/Two.svelte";
  import Three from "./lib/routes/Three.svelte";
  import Tailwind from "./Tailwind.svelte";
  import {Link, Route, Router} from "svelte-routing";
</script>

<Tailwind />

<Router>
    <Route path="/" component={First} />
    <Route path="about" component={Two} />
    <Route path="*" component={Three} />
</Router>