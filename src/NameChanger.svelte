<!-- you are here https://svelte.dev/tutorial/checkbox-inputs -->
<script>
    let userName = '';
    let userEmail = '';
    let userPhone = '';
    let updatedUserPhone = '';

</script>

<h3>Form Input</h3>
<p>Name and Phone will update reactively, email demonstrates submitted</p>
<!-- any event can be set to listen using `on:` -->
<!-- it is possible to pipe event modifiers on listeners https://svelte.dev/tutorial/event-modifiers -->
<form on:submit|preventDefault={()=>updatedUserPhone=userPhone}>
    <label for="userName">Name</label>
    <!-- bind  https://svelte.dev/tutorial/text-inputs -->
    <input id="userName" type="text" placeholder='What is your name?' bind:value={userName}/>
    <label for="userEmail">E-mail</label>
    <input id="userEmail" type="text" placeholder="What is your email?"  bind:value={userEmail}/>
    <label for="userPhone">Phone</label>
    <input id="userPhone" type="text"  placeholder="What is your phone number?" bind:value={userPhone}/>
    <input type=submit value="Submit">
</form>
<!-- todo move output to it's own component using store -->
<h3>Form Output</h3>
<p>Name: {userName}</p>
<p>Email: {userEmail}</p>
<p>Phone Number: {updatedUserPhone}</p>
