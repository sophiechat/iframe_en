**IFRAME**

In this guide we will learn how to use Sophie within a website or web environment. To do this, we must insert it into an HTML element called **IFRAME**.

**Remember that for this implementation it is necessary a basic knowledge of HTML.**

### Dependencies

The following files font-awesome.css, custom.css and jquery are essential.

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/fontawesome/4.7.0/css/font-awesome.min.css">
    <link rel="stylesheet" href="https://sophie-us.stefanini.com/AssistantPublic/Content/css/custom.css">

You can copy and edit these files according to the structure of your website. Remember that the dependency of the Javascript library JQUERY versions 1.11 onwards is essential.

** If this JQUERY file already exists ** on the page to be implemented ** it is not necessary to import it **, if necessary, point to:

    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/1.11.2/jquery.js" integrity="sha256-WMJwNbei5YnfOX5dfgVCS5C4waqvc+/0fV7W2uy3DyU=" crossorigin="anonymous"></script>
	<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/1.11.2/jquery.min.js" integrity="sha256-1OxYPHYEAB+HIz0f4AdsvZCfFaX4xrTD9d2BtGLXnTI=" crossorigin="anonymous"></script>

### Installation:

** IFRAME ** can be considered a small window to show Sophie's chat in web environments. It can be used in a private user area or even your public website.

To install you must follow the steps below:

### [](https://github.com/sophiechat/iframe#1-copiar-e-colar-o-c%C3%B3digo-abaixo-na-p%C3%A1gina-onde-deseja-exibir-chat)1. Copy and paste the code below on the page where you want to view chat:

    <div  class="janela-modal popup-box chat-popup"  
		  id="qnimate"
		  style="display: none;">
		<iframe  frameborder="0"  
				 width="100%"  
				 height="100%"  
				 style="overflow: hidden; 
						border-radius: 0.5em;">
		 </iframe>
	</div>

	<div  class="bubble-ola" style="display: none;">
		<p  class="text-center" style="margin-bottom: 0px;">
			Hello. What can I help you?
		</p>
	</div>

	<div  class="btn-modal">
		<p  class="text-center" 
			style="color: white; 
				   font-size: 14px; 
				   padding-top: 8px;">
			<i  class="fa fa-comment"
				aria-hidden="true"
				style="font-size: 25px; 
					   padding: 12px; 
					   background-color: navy; 
					   border-radius:50%">
			</i>
			<i  class="fa fa-times-circle"
				aria-hidden="true" 
				style="display: none; 
					   position: fixed; 
					   right: 32px; 
					   bottom: 570px;">
		   </i>
		</p>
	</div>

And the JS code must be placed after all the scripts on the same page:

	   <script>
	     $(document).ready(function () {
		    //Chat URL
		    var _chatterURL = 'http://sophie-us.stefanini.com/AssistantPublic/public-covid19/ChatterWeb/index?login=**<YOUR KEY>**';

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
    });
    </script>
    
** READY **, if you followed the steps correctly you will be able to see a similar screen as in the image below:

![](https://sophie-us.stefanini.com/AssistantPublic/Content/images/sophie-widget.png)


**Our file repository**

You can clone or download the files from our repository on [github] (https://github.com/sophiechat/iframe_en/) to test before moving up to a production environment.

In the sample folder there is an example in HTML, the index.html file and its respective dependencies in the folders as shown in the image below.

![](https://doc.sophie.chat/pt/wp-content/uploads/2019/12/sample-github.png)

Notice that the following dependencies are called in the HEAD section of the file:

    <link href="Content/css/opensans.css" rel="stylesheet"/>
	<link href="Content/css/fontawesome/css/font-awesome.css" rel="stylesheet"/>
	<link href="Content/css/quirk2.css" rel="stylesheet"/>
	<link rel="stylesheet" href="Content/css/custom.css">   
	<script src="Scripts/jquery-1.10.2.min.js"></script>
