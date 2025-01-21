<html>
	<button onclick="showChat();">Show Chat Windo</button>
<script type='text/javascript'>
	function initEmbeddedMessaging() {
		try {
			embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'

			window.addEventListener( "onEmbeddedMessagingConversationClosed", () => {
			
				console.log( "Inside Conversation End" );
				embeddedservice_bootstrap.userVerificationAPI.clearSession( true ).then( () => {
    					console.log( 'START::Remove Components' );
					embeddedservice_bootstrap.utilAPI.removeAllComponents();
    					console.log( 'END::Remove Components' );
				} );
			
			} );

			embeddedservice_bootstrap.init(
				'00DWs0000087KS4',
				'MIAW',
				'https://dws0000087ks4mam-dev-ed.develop.my.site.com/ESWMIAW1737481964843',
				{
					scrt2URL: 'https://dws0000087ks4mam-dev-ed.develop.my.salesforce-scrt.com'
				}
			);
		} catch (err) {
			console.error('Error loading Embedded Messaging: ', err);
		}
	};

 	function showChat() {

  		console.log( 'Inside Chat Show' );
    		embeddedservice_bootstrap.utilAPI.showChatButton();

  	}
</script>
<script type='text/javascript' src='https://dws0000087ks4mam-dev-ed.develop.my.site.com/ESWMIAW1737481964843/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>
</html>
