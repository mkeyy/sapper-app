<script context="module">
    export async function preload(page, session) {
        const res = await this.fetch(`${process.env.SAPPER_APP_REST_API_URL}wp/v2/front-page`);
        const data = await res.json();

        return {
            page: data
        };
    }
</script>

<script>
    export let page;
</script>

<svelte:head>
    <title>REST App</title>
</svelte:head>

<section id="ivn-banner">
    <video loop="loop" muted="muted" autoplay="autoplay"
           poster="{page.cmb2.ivn_homepage_settings.ivn_homepage_video_poster}">
        <source data-src="img/ivision_video.mp4" type="video/mp4"
                src="{page.cmb2.ivn_homepage_settings.ivn_homepage_video}">
    </video>

    <h1>{page.cmb2.ivn_homepage_settings.ivn_homepage_title}</h1>
    <h2>{page.cmb2.ivn_homepage_settings.ivn_homepage_subtitle}</h2>
</section>

<style lang="scss">
  section {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    height: 100vh;
    overflow: hidden;
    padding: 20px;

    video {
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      z-index: -1;
      object-fit: cover;
    }

    h1 {
      font-size: 8vmin;
      font-weight: 700;
      line-height: 1.1;
      text-align: center;
      color: var(--c-font);
      margin: 20vh 0 20px;
    }

    h2 {
      font-size: 4.5vmin;
      font-weight: 300;
      line-height: 1;
      text-align: center;
      color: var(--c-font);
      margin: 0;
    }
  }
</style>


