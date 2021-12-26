<script lang="ts">
	import { link } from 'svelte-spa-router'
  const _APP_ENV_: any = process.env._APP_ENV_
</script>

<header>
  <h1>
    <a href="/" use:link>
      {_APP_ENV_.APP_NAME}
    </a>
  </h1>
</header>

<style lang="scss">
  @import '../styles/common.scss';

  header {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: left;
    padding-left: 1rem;

    h1 {
      color: $colorHighlightFocus;
    }

    a,
    a:visited,
    a:active {
      color: $colorHighlightFocus;
    }
  }
</style>