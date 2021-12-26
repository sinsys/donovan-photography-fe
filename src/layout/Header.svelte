<script lang="ts">
  import Navbar from '../components/Navbar.svelte'
  import Logo from '../components/Logo.svelte'

</script>

<header>
  <Logo />
  <Navbar />
</header>

<style lang="scss">
  @import '../styles/common.scss';

  header {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: left;
    position: absolute;
    left: 0;
    height: 100vh;
    padding-left: 1rem;
  }
</style>