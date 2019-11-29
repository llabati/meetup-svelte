<script>
    export let title
    export let subtitle
    export let description
    export let address
    export let contact

    import CustomButton from '../UI/CustomButton.svelte'
</script>

<style>
.meetup-item {
	border: solid 1px #ccc;
	padding: 15px;
    box-shadow: 2px 2px 5px rgba(0, 0, 0, .4);
    width: 50%;
    margin: 15px auto;
}
header {
    color: #ac0095;
    background: #aaa;
    border-bottom: solid 3px #ac0095;
    padding: 10px;
}
header h1 {
    font-family: 'Roboto Slab', serif;
}


</style>
<div class="meetup-item">
    <header>
        <h1>{ title }</h1>
        <h2>{ subtitle }</h2>
    </header>

    <div class="content">
        <p>{ description }</p>
    </div>

    <footer>
        <CustomButton href="{contact}" caption="Contact us" />
        <CustomButton type="button" mode="plain-btn" caption="Show details" />
        <CustomButton type="button" mode="outline" caption="Favorites" />
        <slot></slot>
        
    </footer>

</div>