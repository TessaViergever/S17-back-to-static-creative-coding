<script>
    export let data
</script>
<!-- Dashboard-info: info about dashboard -->
<section>
    <p>{data.infotext.markdown}</p>
</section>

<style>
    section {
        grid-area: dashboard-info;
        border-radius: .5rem;
        padding: 1.5rem;
        background-color: var(--whiteColor);
        box-shadow: var(--boxShadow) 0px 0px 8px;
        transition: .2s;
    }
    /* p {
		font-size: 1.3rem;
		line-height: 1.4;
	} */
    
</style>