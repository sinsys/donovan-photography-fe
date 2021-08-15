<script lang="ts">
	import { link } from 'svelte-spa-router'
  const _APP_ENV_: any = process.env._APP_ENV_

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

<header>
  <h1>
    <a href="/" use:link>
      {_APP_ENV_.APP_NAME}
    </a>
  </h1>
  <ul class="header-nav">
    {#each routes as routeInfo}
    <li>
      <a href="{routeInfo.path}" use:link>{routeInfo.text}</a>
    </li>
    {/each}
  </ul>
</header>

<style lang="scss">
  @import '../styles/common.scss';

  header {
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;

    h1 {
      color: $colorHighlightFocus;
    }

    a,
    a:visited,
    a:active {
      color: $colorHighlightFocus;
    }

    .header-nav {
      display: flex;
      justify-content: flex-end;
      list-style: none;
      flex-wrap: wrap;

      li {
        margin: 1rem;
      }
    }
  }
</style>