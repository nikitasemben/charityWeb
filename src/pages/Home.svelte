<script>
    import { charities } from '../stores/data.js';
    import CharityList from '../components/charityList.svelte';
    import Header from '../components/Header.svelte';
    import Welcome from '../components/welcome.svelte';
    import Promo from '../components/promo.svelte';
    import Footer from '../components/Footer.svelte';
    import Loader from '../components/Loader.svelte';
	let title = "Charity";
    let data;

    charities.subscribe(function(value){
        data = value;
    });

 
    
</script>

<Header />
<Welcome />
{#if !data}
    <Loader />
{:else}
<CharityList charities={data}/>
{/if}
<Promo />
<Footer />
    
