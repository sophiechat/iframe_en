
# Installation


**IFRAME** can be considered a small window to show Sophie's chat in web environments. It can be used in a private user area or even your public website.

To install you must follow the steps below:

**1. Copy and paste the code below on the page where you want to view chat:**

    <div  class="container-fluid conteudo-tela">
	<div  class="janela-modal popup-box chat-popup"  
		  id="qnimate"
		  style="display: none;">
		<iframe  frameborder="0"  
				 width="100%"  
				 height="100%"  
				 style="overflow: hidden; border-radius: 0.5em;">
		 </iframe>
	</div>

	<div  class="bubble-ola" style="display: none;">
		<p  class="text-center" style="margin-bottom: 0px;">
			Hello. What can I help you?
		</p>
	</div>

	<div  class="btn-modal">
		<p  class="text-center" 
			style="color: white; font-size: 14px; padding-top: 8px;">
			<i  class="fa fa-comment"
				aria-hidden="true"
				style="font-size: 25px; padding: 12px; background-color: navy; border-radius:50%">
			</i>
			<i  class="fa fa-times-circle"
				aria-hidden="true" 
				style="display: none; position: fixed; right: 32px;  bottom: 570px;">
		   </i>
		</p>
	</div>
</div>

    <script>
	$(document).ready(function () {
		//Chat URL
		var _chatterURL = 'https://assistant.sophie.chat/<BOTNAME>/ChatterWeb/index?login=visitante';

		//Open Modal
		$(".fa-comment").click(function () {
			$(".janela-modal iframe").attr("src", _chatterURL)
			var janela =  $(".janela-modal");
			janela.stop(true, false).fadeIn();
			$(".fa-comment").stop(true, false).fadeOut();
			$(".fa-times-circle").stop(true, false).fadeIn();
			$(".bubble-ola").hide();
		});
		
		//Close
		$(".fa-times-circle").click(function () {
			$(".janela-modal iframe").removeAttr("src");
			var janela =  $(".janela-modal");
			janela.stop(true, false).fadeOut();
			$(".fa-comment").stop(true, false).fadeIn();
			$(".fa-times-circle").stop(true, false).fadeOut();
		});
		
		$(".bubble-ola").delay(1000).stop(true, false).fadeIn(500);

		$(".bubble-ola").click(function () {
			var ola =  $(".bubble-ola");
			ola.delay(500).stop(true, false).fadeOut(1000);
		});
		
		$(".btn-icon").one("click", function () {
			var nps =  $(".bubble-nps");
			var obrigado =  $(".bubble-obrigado");
			nps.remove();
			obrigado.show();
			obrigado.delay(3000).fadeOut();
		});
	});</script>


**2. Set the bot's URL:**
Change the value of the following variable to the URL of the bot that you want to load the iframe:

    var _chatterURL = 'https://assistant.sophie.chat/<BOTNAME>/ChatterWeb/index?login=visitante';

READY, if you followed the steps correctly you will be able to see the screen below:
![A janela da Sophie se abrirá no canto direto da sua página ](https://doc.sophie.chat/pt/wp-content/uploads/2019/12/iframe-sophie.jpg)

**NOTE**: In the sample folder there is a practical example in HTML.

**Dependencies**
Dependency on the JQUERY Javascript library on minimum versions 1.11

If it already exists on the page to be implemented, it is not necessary to import it, if necessary, point to:

    <script src="https://cdnjs.com/libraries/jquery/1.11.2"></script>

**Wordpress**
For installation in Wordpress the steps are the same, you will need to follow steps 1 and 2 of the installation in the footer.php file. If you do not have access to this file, you can use a plugin to modify it. Remember that there may be limitations according to the template. In this test we used the [Insert Headers and Footers](https://br.wordpress.org/plugins/insert-headers-and-footers/) plugin and we were successful.
