<script>
    export let menu;
    export let segment;
</script>

<header>
    <a rel="prefetch" href="/" class="ivn-brand"><img src="img/logo.png" alt="Ivision.pl"></a>
    <nav>
        <ul>
            {#each menu as link }
                <li>
                    <a rel=prefetch aria-current="{segment === link.url ? 'page' : undefined}"
                       href="{link.url}">{link.title}</a>
                </li>
            {/each}
        </ul>
    </nav>
</header>

<style lang="scss">
  header {
    position: fixed;
    display: flex;
    justify-content: space-between;
    align-items: center;
    top: 0;
    left: 20px;
    right: 20px;
    height: 90px;
    margin: 0;

    .ivn-brand {
      display: flex;

      img {
        width: auto;
        height: 100%;
        max-height: 40px;
        object-fit: contain;
      }
    }

    ul {
      display: flex;
      list-style: none;
      padding: 0;
      margin: 0;

      li {
        margin: 10px;

        & > a {
          font-size: 1.8vmin;
          font-weight: 700;
          line-height: 1;
          text-transform: lowercase;
          color: var(--c-font);
        }
      }
    }
  }


</style>
