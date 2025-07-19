<script lang="ts">
    import ResumeShell from "$lib/components/ResumeShell.svelte";
    import type { ResumeData } from "$lib/types/ResumeData";

    let resumeData: ResumeData = {
        name: "Yikuan",
        email: "yikuan@example.com",
    };
</script>

<div id="editPanel">
    <label>
        Name
        <input type="text" bind:value={resumeData.name} />
    </label>
    <label>
        Email
        <input type="email" bind:value={resumeData.email} />
    </label>
</div>

<div id="previewPanel">
    <ResumeShell data={resumeData} />
    <a href="./resume" target="_blank"
        style:position="absolute" style:top="15px" style:right="15px">
        <button>Open External</button>
    </a>
</div>

<style>
    #editPanel {
        position: fixed;
        top: 0;
        left: 0;
        width: 50%;
        height: 100vh;
        background-color: #242424;
        box-sizing: border-box;
        padding: 36px;
        font-size: 28px;
        color: whitesmoke;
    }

    #editPanel label {
        display: block;
        margin-bottom: 12px;
    }

    #previewPanel {
        position: fixed;
        top: 0;
        right: 0;
        width: 50%;
        height: 100vh;
        background-color: #121212;
        box-sizing: border-box;
        padding: 20px;
    }
</style>