<script>
//export let inputValue
export let type
export let id
export let label
//export let rows


</script>

<div class="form-control">
	<label for={ id }>{ label }</label>
{ #if type === 'textarea' }
	<textarea id={ id } rows=3  on:input></textarea>

{ :else }
	<input { type } { id }  on:input>

{ /if}
</div>

<style>
.form-control {
	width: 80%;
	margin: 10px auto;
}
label {
	text-align: left;
}
input, textarea {
	display: block;
	width: 100%;
}
</style>