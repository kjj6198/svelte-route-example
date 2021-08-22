<script>
  import { Link, Route, Router } from "svelte-routing";
  import BlogPost from "./BlogPost.svelte";
  import Home from "./Home.svelte";
  import ProfileRoute from "./ProfileRoute.svelte";

  let params;
</script>

<main>
  <Router>
    <nav>
      <Link to="/posts/12">Go to post 12</Link>
      <Link to="/">Go Home</Link>
      <Link to="/profile/setting">User Setting</Link>
      <Link to="/profile/address">User address</Link>
    </nav>
    <Route path="/" component={Home} />
    <Route path="/posts/:id" let:params>
      <BlogPost postId={params.id} />
    </Route>
    <Route path="/profile/*" component={ProfileRoute} />
  </Router>
</main>
