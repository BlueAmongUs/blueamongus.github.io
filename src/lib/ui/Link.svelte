<script lang="ts">
    import "$lib/styles/ui/Link.scss";
    export let href: string;
</script>

<a href={href}><slot/></a>