<script>
export let type = "text"
export let caption = ''
export let href = ''
export let mode = 'plain-btn'

import {createEventDispatcher} from 'svelte'

let dispatch = createEventDispatcher()
function launchMsg(){
    dispatch('adding', 'Event fired!')
}
</script>
{ #if href }
<a href={href}>{ caption }</a>
{ :else }
<button class={mode} { type } on:click={launchMsg}>{ caption }</button>
{ /if }

<style>
button {
    padding: 10px;
    background-color: #cf0056;
    color: #fff;
    font-weight: 400;
    border-radius: 10%;
}

.outline {
	background-color: #fff;
	color: #cf0056;
	border: solid 2px #cf0056;
}

button {
	color: #333;
	background-color: #f4f4f4;
	outline: none;
}

button:disabled {
	color: #999;
}

button:not(:disabled):active {
	background-color: #ddd;
}

button:focus {
	border-color: #666;
}
.plain-btn {
    color: #fff;
	background-color: #cf0056;;
}


</style>