<script>
import MeetupItem from './MeetupItem.svelte'
export let meetups
</script>

<style>
section {
    width: 100%;
    display: grid;
    grid-template-columns: 1fr;
    grid-gap: 1rem;
}

small {
    display: block;
    font-size: .8rem;
    text-align: center;
}

@media (min-width: 768px) {
    section{
        
    }
}

</style>

<section id="meetups">
    { #each meetups as meetup }
		<MeetupItem  
		title={meetup.title} 
		subtitle={meetup.subtitle} 
		description={meetup.description} 
		address={meetup.address} 
		contact={meetup.contact}>
        <small>Approved by us</small></MeetupItem> 
	{ /each }
</section>