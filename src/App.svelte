<script>
	import Header from './UI/Header.svelte'
	import MeetupGrid from './Meetups/MeetupGrid.svelte'
	import TextInput from './UI/TextInput.svelte'
	import CustomButton from './UI/CustomButton.svelte'
	import { onMount, tick } from 'svelte'

	let meetups = [
		{
			id: 'M1',
			title: 'Code Bootcamp',
			subtitle: 'Learn to code in 2 hours',
			description: 'You will meet some experts who teach you how to code the fastest way.',
			address: 'Boulevard Montmartre, Paris',
			contact: 'contact@nodeschool.com'
		},
		{
			id: 'M2',
			title: 'JavaScript Bootcamp',
			subtitle: 'Discover the basics of JavaScript',
			description: 'Still Python, PHP or Java developers, meet JavaScript and let be conquered by it!',
			address: 'Europole, Lille',
			contact: 'contact@europole.com'
		},
		{
			id: 'M3',
			title: 'Svelte Bootcamp',
			subtitle: 'Discover Svelte and start a brand new project',
			description: 'Meet the founder of Svelte and adopt Svelte for a project of yours.',
			address: 'Centre Bellini, La Défense',
			contact: 'meetups@altran.com'
		},
	]
	let title = ''
	let subtitle = ''
	let description = ''
	let address = ''
	let contact = ''
	let type = ""

	function addMeetup(event){
		event.preventDefault()
		let newMeetup = {}
		newMeetup.title = title
		newMeetup.subtitle = subtitle
		newMeetup.description = description
		newMeetup.address = address
		newMeetup.contact = contact

		meetups = [ ...meetups, newMeetup ]
		console.log(meetups)
	}

	onMount(async() => {
		console.log('About to be mounted')
		await tick()
		console.log('Mounted!!!')
	})
</script>

<Header />

<main>
	<form on:submit={ addMeetup }>
	<TextInput id="title" label="Title" type = "text" value={title} on:input={ event => title = event.target.value } />
	<TextInput id="subtitle" label="Subtitle" type = "text" value={subtitle} on:input={ event => subtitle = event.target.value } />
	<TextInput id="description" label="Short description" type = "textarea" value={description} on:input={ event => description = event.target.value } />
	<TextInput id="address" label="Address" type="text" value={address} on:input={ event => address = event.target.value } />
	<TextInput id="contact" label="Contact" type="email" value={contact} on:input={ event => contact = event.target.value } />
		
	<CustomButton type="submit" caption="Add meetup" on:adding={(event) => console.log(event.detail)}/>
		
	</form>
	<MeetupGrid meetups={meetups}/>

</main>
<style>

main {
	text-align: center;
	padding: 1rem;
	max-width: 240px;
	margin: 45px auto;
	font-family: 'Open Sans', sans-serif;
}

h2 {
	color: #ff3e00;
	text-transform: uppercase;
	font-size: 4rem;
	font-weight: 100;
}

form {
	background-color: rgb(244, 230, 230);
	width: 50%;
	margin: 10px auto;
}


@media (min-width: 640px) {
	main {
		max-width: none;
	}
}
</style>