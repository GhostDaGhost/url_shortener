<script lang="ts">
    export let value: string;
</script>

<div id="urltoshorten_container">
    <div class="label_container">
        <span class="label">Input:</span>
    </div>

    <div class="input_container">
        <input
            id="urltoshorten"
            class="inputbox"
            type="text"
            name="urltoshorten"
            placeholder="Enter URL to shorten here..."
            bind:value={value}
        >
    </div>
</div>

<style lang="less">
    @import '../styles/UrlToShorten';
</style>
