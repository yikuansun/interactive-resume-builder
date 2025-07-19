<script lang="ts">
    export let name: string;
    export let pageWidth: number = 2550;
    export let pageHeight: number = 3300;
</script>

<svg viewBox="0 0 2550 3300" xmlns="http://www.w3.org/2000/svg" width="100%" height="100%">
    <defs>
        <rect id="page-clip" x="0" y="0" width={pageWidth} height={pageHeight} />
    </defs>
    <g clip-path="url(#page-clip)">
        <rect x="0" y="0" width={pageWidth} height={pageHeight} fill="white" />
        <foreignObject x="0" y="0" width={pageWidth} height={500} style:border-bottom="10px solid grey">
            <div style:display="flex" style:flex-direction="column" style:align-items="center" style:justify-content="center"
                style:width="100%" style:height="100%">
                <div style:font-size="150px">{name}</div>
            </div>
        </foreignObject>
    </g>
</svg>