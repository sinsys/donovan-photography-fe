<script lang="ts">
	import { link } from 'svelte-spa-router'
  
  interface RouteInfo {
    text: string
    path: string
    auth?: boolean
  }

  const routes: RouteInfo[] = [
    { text: 'Portfolio', path: '/portfolio', auth: false },
    { text: 'About', path: '/about', auth: false },
    { text: 'Quote', path: '/quote', auth: false },
    { text: 'Photos', path: '/photos/123', auth: true },
    { text: 'SinglePhoto', path: '/photos/123/abc', auth: true },
    { text: 'I\'m broken', path: '/somebrokenlink', auth: false }
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
    color: $colorHighlightFocus;
  }

  .header-nav {
    display: flex;
    justify-content: flex-start;
    list-style: none;
    flex-wrap: wrap;
    margin: 0;
    padding: 0;

    li {
      margin: 0 1rem;
    }
  }
</style>