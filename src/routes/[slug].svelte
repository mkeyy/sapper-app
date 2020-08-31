<script context="module">
    export async function preload(page, session) {
        const res = await this.fetch(`${process.env.SAPPER_APP_REST_API_URL}wp/v2/pages?slug=${page.params.slug}`);
        const data = await res.json();

            return {
                page: data[0]
            };
    }
</script>

<script>
    export let page;
</script>

<h1>{page.title.rendered}</h1>

<style>

</style>