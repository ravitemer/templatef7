<App { ...f7params }>

	<!-- Your main view, should have "view-main" class -->
	<View main class="safe-areas" url="/" />

	<LoginScreen id="my-login-screen">
		<View>
			<Page loginScreen>
				<LoginScreenTitle>Login</LoginScreenTitle>
				<List form>
					<ListInput type="text" name="username" placeholder="Your username" bind:value={username} />
					<ListInput type="password" name="password" placeholder="Your password" bind:value={password} />
				</List>
				<List>
					<ListButton title="Sign In" onClick={()=> alertLoginData()} />
				</List>
				<BlockFooter>
					Some text about login information.<br />Click "Sign In" to close Login Screen
				</BlockFooter>
			</Page>
		</View>
	</LoginScreen>
</App>
<script>
  import { onMount } from "svelte";

  import {
    f7,
    f7ready,
    App,
    Panel,
    Views,
    View,
    Popup,
    Page,
    Navbar,
    Toolbar,
    NavRight,
    Link,
    Block,
    BlockTitle,
    LoginScreen,
    LoginScreenTitle,
    List,
    ListItem,
    ListInput,
    ListButton,
    BlockFooter
  } from "framework7-svelte";

  import routes from "../js/routes";
  import store from "../js/store";

  // Framework7 Parameters
  let f7params = {
    name: "templatef7", // App name
    theme: "ios", // Automatic theme detection

    // App store
    store: store,
    // App routes
    routes: routes
  };
  // Login screen demo data
  let username = "";
  let password = "";

  function alertLoginData() {
    f7.dialog.alert("Username: " + username + "<br>Password: " + password, () => {
      f7.loginScreen.close();
    });
  }
  onMount(() => {
    f7ready(() => {
      // Call F7 APIs here
    });
  });
</script>