<script>
    import { onMount } from 'svelte';
    import CharityList from '../components/charityList.svelte';
    import Header from '../components/Header.svelte';
    import Welcome from '../components/welcome.svelte';
    import Promo from '../components/promo.svelte';
    import Footer from '../components/Footer.svelte';
    import Loader from '../components/Loader.svelte';
	let title = "Charity";
    let data = getData();

    async function getData(){
        const res = await fetch('https://charity-api-bwa.herokuapp.com/charities');
        const data = await res.json();

        if(res.ok){
            return data;
        }else {
            throw new Error(data);
        }
    }
    
</script>

<Header />
<Welcome />
{#await data}
    <Loader />
{:then charities}
<CharityList {charities}/>
{/await}
<Promo />
<Footer />
    
