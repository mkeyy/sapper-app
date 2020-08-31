<script context="module">
    export async function preload(page, session) {
        const res = await this.fetch(`${process.env.SAPPER_APP_REST_API_URL}wp/v2/menus/main`)
        const data = await res.json()

        return {
            menu: data
        }
    }
</script>

<script>
    import Header from '../components/Header.svelte';

    export let menu;
    export let segment;
</script>

<style lang="scss">
    :root {
        --c-background: #181818;
        --c-font: #fff;
        --c-border: #ccc;
    }
</style>

<Header {segment} {menu}/>

<slot></slot>