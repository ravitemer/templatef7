<Page name="home">
	<div class="login-col">
		<div class="login-top-text">
			<span class="text-heading-top">Hey there,</span><br>
			<span on:click={()=> console.log(JSON.stringify(fields))} class="text-heading">Create account</span>
		</div>
		<form class="login-form" on:submit|preventDefault={onSubmit}>
			<div class="login-fields">
				<div class="fields">
					{#each Object.entries(fields) as [key,{type,placeholder}],i (i)}
					<label for={key}></label>
					<input class="login-input" name={key} id={key} type={type} placeholder={placeholder} />
					{/each}
				</div>
				<button type="submit">Submit</button>
			</div>

		</form>
	</div>



</Page>
<style lang="postcss">
  .login-form {
    @apply h-full;
  }
  .login-fields {
    @apply flex flex-col h-full justify-between items-center;
  }
  .login-col {
    @apply flex h-full flex-col items-center p-8 text-center bg-blue-400;
  }
  .text-heading-top {
    @apply text-gray-700 font-medium text-center;
  }
  .text-heading {
    @apply text-black font-bold text-xl font-serif text-center;
  }
</style>
<script>
  import {
    Page,
    Navbar,
    NavLeft,
    NavTitle,
    NavTitleLarge,
    NavRight,
    Link,
    Toolbar,
    Block,
    BlockTitle,
    List,
    ListItem,
    Row,
    Col,
    Button
  } from "framework7-svelte";
  let fields = {
    firstname: {
      type: "text",
      placeholder: "First name",
      value: ""
    },
    lastname: {
      type: "text",
      placeholder: "Last name",
      value: ""
    },
    email: {
      type: "email",
      placeholder: "Email",
      value: ""
    },
    password: {
      type: "password",
      placeholder: "Password",
      value: ""
    }
  };
  function onSubmit(e) {
    const formData = new FormData(e.target);
    const data = {};
    for (let field of formData) {
      const [key, value] = field;
      data[key] = value;
    }
    console.log(data);
  }
</script>