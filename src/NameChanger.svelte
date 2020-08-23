<script>

    export let appTitle = 'Form';
    let userName = '';
    let userEmail = '';
    let userPhone = '';
    let updatedUserPhone = '';

    const htmlString = '&lt;div&gt';
</script>

<style>
    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 3em;
        font-weight: 100;
    }
</style>

<h1>Welcome To: {appTitle}</h1>
<p>
    Random HTML string just because ➡
    {@html htmlString}
</p>

<h2>Form Input</h2>
<p>Name and Phone will update reactively, email demonstrates submitted</p>
<form on:submit|preventDefault={()=>updatedUserPhone=userPhone}>
    <label for="userName">Name</label>
    <input id="userName" type="text" placeholder='What is your name?' bind:value={userName}/>
    <label for="userEmail">E-mail</label>
    <input id="userEmail" type="text" placeholder="What is your email?"  bind:value={userEmail}/>
    <label for="userPhone">Phone</label>
    <input id="userPhone" type="text"  placeholder="What is your phone number?" bind:value={userPhone}/>
    <input type=submit value="Submit">
</form>
<!-- todo move output to it's own component useing store -->
<h2>Form Output</h2>
<p>Name: {userName}</p>
<p>Email: {userEmail}</p>
<p>Phone Number: {updatedUserPhone}</p>
