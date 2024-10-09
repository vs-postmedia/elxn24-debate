<script>
    // COMPONENTS
    import { onMount } from 'svelte';

    // IMAGES
    import ebyImg from '$images/eby-mug.png';
    import rustadImg from '$images/rustad-mug.png';
    import furstenauImg from '$images/furstenau-mug.png';
    

    // DATA
    const dataUrl = 'https://raw.githubusercontent.com/ajstarks/dubois-data-portraits/master/challenge/2024/challenge03/data.csv';
</script>

<header>
    <h1>In their words</h1>
    <p class="subhead">How long each each party leader spoke and what they spoke about during B.C.’s televised election debate on Oct. 8.</p>
</header>

<main>
    <ul id="legend">
        <li class="housing">
            <span class="swatch"></span>
            <p>Housing</p>
        </li>
        <li class="economy">
            <span class="swatch"></span>
            <p>Economy</p>
        </li>
        <li class="healthcare">
            <span class="swatch"></span>
            <p>Healthcare</p>
        </li>
        <li class="climate">
            <span class="swatch"></span>
            <p>Climate</p>
        </li>
        <li class="fn">
            <span class="swatch"></span>
            <p>First Nations</p>
        </li>
        <li class="seniors">
            <span class="swatch"></span>
            <p>Seniors</p>
        </li>
        <li class="drugs">
            <span class="swatch"></span>
            <p>Toxic drugs</p>
        </li>
        <li class="crime">
            <span class="swatch"></span>
            <p>Crime</p>
        </li>
    </ul>

    <ul id="viz">
        <li>
            <span>
                <img class="ndp" src={ebyImg} />
                <!-- <p>David Eby</p> -->
            </span>
            <iframe src='https://flo.uri.sh/visualisation/19724112/embed' title='Interactive or visual content' frameborder='0' scrolling='no' style='height:75px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>
        </li>
        <li>
            <span>
                <img class="cons" src={rustadImg} />
                <!-- <p>John Rustad</p> -->
            </span>
            <iframe src='https://flo.uri.sh/visualisation/19737292/embed' title='Interactive or visual content' frameborder='0' scrolling='no' style='height:75px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>
            
        </li>
        <li>
            <span>
                <img class="greens" src={furstenauImg} />
                <!-- <p>Sonia Fursteau</p> -->
            </span>
            <iframe src='https://flo.uri.sh/visualisation/19737286/embed' title='Interactive or visual content' frameborder='0' scrolling='no' style='height:75px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>
        </li>
    </ul>
</main>

<footer>
    <p class="note">NOTE: tk.</p>
    <p class="source">Source: Postmedia analysis</p>
</footer>
  
<style>
    @import '$css/normalize.css';
    @import '$css/fonts.css';
    @import '$css/colors.css';
    @import '$css/app.css';

    header {
		margin-bottom: 2rem;
	}
    #legend {
        display: flex;
        flex-wrap: wrap;
    }
    #legend li {
        display: flex;
    }
    #legend .swatch {
        display: block;
        height: 12px;
        margin: 3px 5px 3px 8px;
        width: 12px;
    }
    #legend .economy > span {
        background-color: #a28ebd;
    }
    #legend .healthcare > span {
        background-color: #0062A3;
    }
    #legend .climate > span {
        background-color: #009775;
    }
    #legend .housing > span {
        background-color: #9B3F86;
    }
    #legend .other > span {
        background-color: #d1d2d4;
    }
    #legend .fn > span {
        background-color: #6D6E70;
    }
    #legend .drugs > span {
        background-color: #795b9e;
    }
    #legend .seniors > span {
        background-color: #b174a2;
    }
    #legend .crime > span {
        background-color: #6D8EBF;
    }
    #legend .other > span {
        background-color: #d1d2d4;
    }
    #viz ul li {
        display: flex; 
        justify-content: flex-start;
    }
    #viz li {
        margin: 30px 0;
    }
    #viz img {
        border-radius: 50%;
        margin-top: -10px;
        width: 80px;
    }
    #viz li p {
        text-align: center;
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
