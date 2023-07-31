<script lang="ts">
    import axios from "axios";
    import HeaderText from './components/HeaderText.svelte';
    import UrlToShorten from './components/UrlToShorten.svelte';

    let targetURL: string;
    let shorturl: string;

    /**
        * A function that is triggered when the user presses the shorten URL button. Sends an API request to get shorter link of what was sent.
        * @returns `void` - This returns nothing.
    */
    const ShortenURL = () => {
        const linkRequest = {
            destination: targetURL,
            domain: { fullName: "rebrand.ly" }
        };

        axios.post('https://api.rebrandly.com/v1/links', linkRequest, {
            headers: {
                "Content-Type": "application/json",
                "apikey": '6ac5bec1bcab4e57824ca06519abd83b',
                //"workspace": "YOUR_WORKSPACE_ID"
            }
        }).then(response => {
            //console.log(response);
            shorturl = response?.data?.shortUrl ?? '';
        }).catch(error => {
            //console.log(error);
        });
    }
</script>

<main id="outercontainer">
    <div id="innercontainer">
        <HeaderText />

        <hr id="divider">

        <UrlToShorten bind:value={targetURL} />

        <div id="shortenedurl_container">
            <div class="label_container">
                <span class="label">Output:</span>
            </div>
        
            <div class="input_container">
                <input
                    id="shortenedurl"
                    class="inputbox"
                    type="text"
                    name="shortenedurl"
                    placeholder="Shortened link will be here..."
                    disabled 
                    readonly
                    bind:value={shorturl}
                >
            </div>
        </div>

        <div id="shortenurl_button_container">
            <button id="shortenurl_button" on:click={ShortenURL}>Shorten URL</button>
        </div>
    </div>
</main>

<style lang="less">
    @import './styles/App';
</style>
