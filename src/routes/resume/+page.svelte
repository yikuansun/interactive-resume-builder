<script lang="ts">
    import ResumeShell from "$lib/components/ResumeShell.svelte";

    function print() {
        window.print();
    }
</script>

<div id="main">
    <ResumeShell data={{ name: "Yikuan", email: "yikuan@example.com" }} />
</div>

<div id="controls">
    <button on:click={print}>Print</button>
    <br /> <br />
    <button on:click={() => {
        let a = document.createElement("a");
        a.href = window.URL.createObjectURL(new Blob([document.documentElement.outerHTML], { type: "text/html" }));
        a.download = "resume.html";
        a.click();
    }}>Download</button>
</div>

<svelte:window 
    on:keydown={(e) => {
        if (e.key === "p" && (e.ctrlKey || e.metaKey)) {
            e.preventDefault();
            print();
        }
    }}
/>

<style>
    #main {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: #121212;
    }

    #controls {
        position: fixed;
        top: 0;
        right: 0;
        box-sizing: border-box;
        padding: 20px;
        text-align: right;
    }

    @media print {
        @page {
            margin: 0;
        }

        #controls {
            display: none;
        }

        #main {
            background-color: transparent;
        }
    }
</style>