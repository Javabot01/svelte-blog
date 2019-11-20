<script>
  import { Router, Route } from "svelte-routing";
  import Navbar from "./components/Navbar.svelte";
  import News from "./pages/News.svelte";
  import About from "./pages/About.svelte";
  import Listitem from "./components/Listitem.svelte";
</script>

<Router>
  <Navbar />
  <div class="container">
    <div class="row mt-5">
      <div class="col-md-8">
        <Route path="/" component={News} />
        <Route path="/about" component={About} />
      </div>
      <div class="col-md-4">
        <div class="card">
          <div class="card-header">Featured</div>
          <ul class="list-group list-group-flush">
            <Listitem item={'Business'} />
            <Listitem item={'Entertainment'} />
            <Listitem item={'Health'} />
            <Listitem item={'Science'} />
            <Listitem item={'Sports'} />
            <Listitem item={'Technology'} />
          </ul>
        </div>
      </div>
    </div>
  </div>
</Router>
