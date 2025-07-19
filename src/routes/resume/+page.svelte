<script lang="ts">
    import ResumeShell from "$lib/components/ResumeShell.svelte";
</script>

<div style:width="100vw" style:height="100vh" style:background-color="black"
    style:position="fixed" style:top="0" style:left="0">
    <ResumeShell data={{ name: "Yikuan", email: "yikuan@example.com" }} />
</div>

<style>
    @media print {
        @page {
            margin: 0;
        }
    }
</style>