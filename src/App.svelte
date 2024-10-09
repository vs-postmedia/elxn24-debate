<script>
    // COMPONENTS
    import { onMount } from 'svelte';
    import { csvParse } from 'd3-dsv';

    // IMAGES
    import ebyImg from '$images/eby-mug.png';
    import rustadImg from '$images/rustad-mug.png';
    import furstenauImg from '$images/furstenau-mug.png';
    

    // DATA
    const dataUrl = 'https://raw.githubusercontent.com/ajstarks/dubois-data-portraits/master/challenge/2024/challenge03/data.csv';

    // VARIABLES
    let data;

    async function fetchData(url) {
        const resp = await fetch(url);
        data = await resp.text();
        return csvParse(data);
    }

    async function init() {
        // fetch remote data
        data = await fetchData(dataUrl);
        // console.log(data);
    }

    onMount(init);
</script>

<header>
    <h1>In their words</h1>
    <p class="subhead">How long each each party leader spoke and what they talked about during B.C.’s televised election debate on Oct. 8.</p>
</header>

<main>
    <ul id="legend">
        <li class=""></li>
    </ul>
    <ul id="viz">
        <li>
            <img class="ndp" src={ebyImg} />
            <iframe src='https://flo.uri.sh/visualisation/19724112/embed' title='Interactive or visual content' frameborder='0' scrolling='no' style='height:100px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>
        </li>
        <li>
            <img class="cons" src={rustadImg} />
            <iframe src='https://flo.uri.sh/visualisation/19724112/embed' title='Interactive or visual content' frameborder='0' scrolling='no' style='height:100px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>
            
        </li>
        <li>
            <img class="greens" src={furstenauImg} />
            <iframe src='https://flo.uri.sh/visualisation/19724112/embed' title='Interactive or visual content' frameborder='0' scrolling='no' style='height:100px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>
        </li>
    </ul>
</main>

<footer>
    <p class="note">NOTE: tk.</p>
    <p class="source">Source:  <a href="https:vancouversun.com" target="_blank">TK</a></p>
</footer>
  
<style>
    @import '$css/normalize.css';
    @import '$css/fonts.css';
    @import '$css/colors.css';
    @import '$css/app.css';

    header {
		margin-bottom: 2rem;
	}
    #viz ul li {
        display: flex; 
        justify-content: flex-start;
    }
    #viz li {
        margin: 15px 0;
    }
    #viz img {
        border-radius: 50%;
        margin-top: -10px;
        width: 80px;
    }
    #viz iframe {
        width: calc(100% - 100px);
    }
    #viz img.ndp {
        border: 4px solid #FD4E27;
    }
    #viz img.cons {
        border: 4px solid #004AAD;
    }
    #viz img.greens {
        border: 4px solid #009A44;
    }
</style>
