<script lang="ts">
	import { link } from 'svelte-spa-router'
  
  interface RouteInfo {
    text: string
    path: string
    auth?: boolean
  }

  const routes: RouteInfo[] = [
    { text: 'portfolio', path: '/portfolio', auth: false },
    { text: 'about', path: '/about', auth: false },
    { text: 'contact', path: '/contact', auth: false }
  ]

</script>

<ul class="header-nav">
  {#each routes as routeInfo}
  <li>
    <a href="{routeInfo.path}" use:link>{routeInfo.text}</a>
  </li>
  {/each}
</ul>

<style lang="scss">
  @import '../styles/common.scss';
  
  a,
  a:visited,
  a:active {
    color: $colorPrimaryAlt;
    text-decoration: none;
  }

  .header-nav {
    display: flex;
    justify-content: flex-start;
    list-style: none;
    flex-wrap: wrap;
    flex-direction: column;
    height: 60%;
    justify-content: space-evenly;
    margin: 0;
    padding: 0;

    li {
      margin: 0 2rem;
      font-size: 2rem;
      text-transform: uppercase;
      
      a {
        display: inline-block;
        font-family: $font-federo;
        font-size: 5vh;
        transition: transform 0.5s ease-in-out, color 0.3s ease-in-out;

        &:hover {
          color: $colorHighlightFocus;
          transform: scale(1.2) translateX(3rem);
        }
      }
    }
  }
</style>