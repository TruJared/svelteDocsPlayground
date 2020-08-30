<script>
import {user} from './stores.js';
let userPhone;

    // * not an ideal way to handle this, but illustrates stores being used in the script tag * //
    function capitalize() {
        if(typeof $user.name !== 'string')return;
        return $user.name = $user.name.charAt(0).toUpperCase() + $user.name.slice(1);

    }



</script>

<h3>Form Input</h3>
<p>Name and Phone will update reactively, email demonstrates submitted</p>
<!-- any event can be set to listen using `on:` -->
<!-- it is possible to pipe event modifiers on listeners https://svelte.dev/tutorial/event-modifiers -->
<form on:submit|preventDefault={()=>$user.phone = userPhone}>
    <label for="userName">Name</label>
    <!-- bind  https://svelte.dev/tutorial/text-inputs -->
    <input id="userName" type="text" placeholder='What is your name?' on:keyup={() => capitalize()} bind:value={$user.name}/>
    <label for="userEmail">E-mail</label>
    <input id="userEmail" type="text" placeholder="What is your email?"  bind:value={$user.email}/>
    <label for="userPhone">Phone</label>
    <input id="userPhone" type="text"  placeholder="What is your phone number?" bind:value={userPhone}/>
    <input type=submit value="Submit">
</form>
