<script>
    import CharityList from '../components/charityList.svelte';
    import Header from '../components/Header.svelte';
    import Welcome from '../components/welcome.svelte';
    import Promo from '../components/promo.svelte';
    import Footer from '../components/Footer.svelte';
    import { charities } from '../data/charities.js';
	let title = "Charity";
</script>

<Header />
<Welcome />
<CharityList {charities}/>
<Promo />
<Footer />
    
