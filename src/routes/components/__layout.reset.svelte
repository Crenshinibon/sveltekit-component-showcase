<script context="module">

  import { dev } from '$app/env';
  
  export const load = ({page}) => {
    if (!dev) {
      return {
        status: 404,
        error: new Error(`Could not load components url`)
      };
    }

    return {}
  }
  
</script>

<div class="wrapper">
  <nav>
    <a href="/components/button">Button</a>
  </nav>
  <div class="component-wrapper">
    <slot></slot>
  </div>
</div>

<style>
  :global(html,body) {
    padding: 0;
    margin: 0;

    height: 100%;
    width: 100%;
  }
  

  .wrapper {
    display: flex;
    flex-direction: row;
    justify-content: stretch;
    height: 100vh;
  }

  nav {
    background-color: black;
    padding: 1rem;
  }

  nav a {
    color: whitesmoke
  }

  .component-wrapper {
    background-color:mintcream;

    flex-grow: 1;
    padding: 1rem;
  }


</style>