<script>
	import TextEditor from './components/TextEditor.svelte';
	import NavBar from './components/NavBar.svelte';
    import FormDemo from './components/FormDemo.svelte';

	let headingTextForEditor = 'Markdown Editor'
	let tabLabels = [
		{name : 'Text Editor', val: 1},
		{name: 'Form', val: 2}
	]
	let clickedTab = 1;

	let defaultStudent = {
		firstname: 'Udith',
		lastname: 'Indrakantha',
		dob: new Date('1997/11/17'),
		university: 'University of Moratuwa',
	}

	let title = "Form by Udith";

	function onTabClick(event) {
		clickedTab = event.detail.val;
	}
</script>


<main class="container">
	<NavBar {tabLabels} on:tabPressed= {onTabClick} />
	{#if clickedTab == 1}
	<TextEditor headingText={headingTextForEditor} />
	{:else}
	<FormDemo {...defaultStudent} {title}/>  
	{/if}

</main>


<style>
	.container{
        background: #ff7b00d6;
        padding:10px 30px;
    }
</style>