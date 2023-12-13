<script>
	import Infotext from '../lib/components/infotext.svelte';
	import TrashRemoved from '../lib/components/trash-removed.svelte';
	import Map from '../lib/components/map.svelte';
	import Trashgraph from '../lib/components/trashGraph.svelte';
	import ChartContinents from "../lib/components/chartContinents.svelte";
	import ChartRiverOcean from "../lib/components/chartRiverOcean.svelte";
	import SystemStatus from "../lib/components/system-status.svelte"
	export let data;
</script>

<svelte:head>
	<title>Dashboard The Ocean Cleanup</title>
</svelte:head>



<ul class="container">

    <li class="card card-tall card-wide"></li>
	<li class="card card-tall card card-tall"></li>
	<li class="card">1</li>
	<li class="card">2</li>
	<li class="card">3</li>
	<li class="card">4</li>
	<li class="card">5</li>
	<li class="card">6</li>
	<li class="card">7</li>
	<li class="card">8</li>
	<li class="card">9</li>
	<li class="card">10</li>
	
</ul>


<section class="main">
	<div class="container2">

		<section class="panel more">
			<h2>More about</h2>
			<table class="table-more">
				<tr class="more-row">
					<td class="more-icon">
						<a href="/" class="more-link">
							<!-- add icon -->
							Our river technology
						</a>
					</td>
					<td class="arrow">
						<!-- add icon -->
					</td>
				</tr>

				<tr class="more-row">
					<td class="more-icon">
						<a href="/" class="more-link">
							<!-- add icon -->
							The economic impact
						</a>
					</td>
					<td class="arrow">
						<!-- add icon -->
					</td>
				</tr>

				<tr class="more-row">
					<td class="more-icon">
						<a href="/" class="more-link">
							<!-- add icon -->
							Plastic sources
						</a>
					</td>
					<td class="arrow">
						<!-- add icon -->
					</td>
				</tr>

				<tr class="more-row">
					<td class="more-icon">
						<a href="/" class="more-link">
							<!-- add icon -->
							Donate
						</a>
					</td>
					<td class="arrow">
						<!-- add icon -->
					</td>
				</tr>

				<span>
					<tr class="more-row">
						<td class="more-icon">
							<a href="/" class="more-link">
								<!-- add icon -->
								Sign up to newsletter
							</a>
						</td>
						<td class="arrow">
							<!-- add icon -->
						</td>
					</tr>
				</span>
			</table>
		</section>
	</div>
</section>
<!-- End main section -->
<section>
	<TrashRemoved data={data.dataApi.totals} text={data.dataHygraph} />
	<TrashRemoved data={data.dataApi.totals} text={data.dataHygraph}></TrashRemoved>
	<ChartRiverOcean data={data} />
	<ChartContinents {data} />
	<Trashgraph {data} />
	<Map {data} />
	<Infotext data={data.dataHygraph.dashboard.infotext} />
	<SystemStatus data={data} />
</section>



<style>
	/* Proxima font */
	@font-face {
		font-family: 'Proxima';
		src: url('/ProximaNovaFont.otf') format('opentype') weight('normal');
		src: url('/Proxima-Nova-Bold.otf') format('opentype') weight('bold');
	}

	/* Base */
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
		font-family: 'Proxima', sans-serif;
	}

	:root {
		--darkBlue: #143653;
		--trashRemovedBackground: white;
		--lightBlue: #5cc8de;
		--whiteColor: #ffffff;
		--lightGray: #f7f7f7;
		--accentGray: rgb(228, 228, 228);
		--textColor: #143653;
		--boxShadow: rgba(128, 128, 128, 0.132);
		--color: rgb(212, 212, 212);
		--textSize: 1.2rem;
		--iconSize: 2rem;
	}

	/* Als darkmode de standaard instelling is */
	@media (prefers-color-scheme: dark) {
		:root {
			--darkBlue: #ffffff;
			--trashRemovedBackground: #143653;
			--lightBlue: #5cc8de;
			--whiteColor: #143653;
			--lightGray: #0d2437;
			--accentGray: rgb(228, 228, 228);
			--textColor: #ffffff;
			--boxShadow: rgba(128, 128, 128, 0);
			--color: rgb(212, 212, 212);
			--textSize: 1.2rem;
			--iconSize: 2rem;
		}
	}

	:global(html) {
		font-size: 62.5%;
		scroll-behavior: smooth;
	}

	:global(body) {
		background-image:radial-gradient(
			Black 5%,
			lightskyblue 10%,
			Yellow 2%,
			Orange 15%,
			Darkblue 50%,
			transparent
		);
		color: var(--textColor);
		position: relative;
	}

	h2 {
		line-height: 1.2;
		font-weight: 500;
		color: var(--darkBlue);
		margin-bottom: 1rem;
	}

	h3 {
		font-size: 1.3rem;
		font-weight: 500;
	}

	a {
		text-decoration: none;
	}


/* GRID CREATIVE CODING */

.container {
  display: grid;
  gap: 1rem;
  grid-template-columns: repeat(auto-fill,minmax(240px,1fr)); 
  grid-auto-rows: 240px;
  margin: 10em;
}

.card {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

	background-image:linear-gradient(
			rgb(62, 41, 41) 8%,
			hotpink 10%,
			Orange 20%,
			Rebeccapurple 75%);

    font-size: 3rem;
    color: #F08080;
    box-shadow: rgba(3, 8, 20, 0.1) 0px 0.15rem 0.5rem, rgba(2, 8, 20, 0.1) 0px 0.075rem 0.175rem;
    height: 100%;
    width: 100%;
    border-radius: 4px;
    transition: all 500ms;
    overflow: hidden;

 }
.card:hover {
    box-shadow: rgba(2, 8, 20, 0.1) 0px 0.35em 1.175em, rgba(2, 8, 20, 0.08) 0px 0.175em 0.5em;
    transform: translateY(-3px) scale(1.1);
 }

 @media only screen and (min-width: 600px){
.card-tall {
  grid-row: span 2/auto;
}

.card-wide {
  grid-column: span 2/auto;
}
}

</style>
