---
layout: page
title: Contact
subtitle: 
---

		<section class="contact-form-section mb-5">
			<div class="container">
				<form action="https://formspree.io/mqklnqqe" class="contact-form p-5 col-lg-9 mx-lg-auto theme-bg-light shadow" id="contact-form" method="post" name="contact-form">
					<h3 class="text-center">Ask A Question</h3>
					<div class="mb-3 text-center">
						For pre-sale and general questions, please use the form below.
					</div>
					<div class="form-row">
						<div class="form-group col-md-6">
							<label class="sr-only" for="cname">Name</label> <input class="form-control" id="cname" name="name" placeholder="Name" required="">
						</div>
						<div class="form-group col-md-6">
							<label class="sr-only" for="cemail">Email</label> <input class="form-control" id="cemail" name="_replyto" placeholder="Email" required="" type="email">
						</div>
						<div class="form-group col-12">
							<label class="sr-only" for="cmessage">Your message</label> 
							<textarea class="form-control" id="cmessage" name="message" placeholder="Enter your message" required="" rows="10"></textarea>
						</div>
						<div class="form-group col-12">
							<button class="btn btn-block btn-success py-2" id="my-form-button" type="submit">Submit</button>
						</div>
					</div>
					<p id="my-form-status"></p>
				</form>
			</div>
		</section>
	</div>

	<script>
	window.addEventListener("DOMContentLoaded", function() {

	   // get the form elements defined in your form HTML above
	   
	   var form = document.getElementById("contact-form");
	   var button = document.getElementById("my-form-button");
	   var status = document.getElementById("my-form-status");

	   // Success and Error functions for after the form is submitted
	   
	   function success() {
	     button.style = "display: none ";
	     form.reset();
	     status.innerHTML = "Success! Thank you for contacting us. We will get back to you soon.";
	   }

	   function error() {
	     status.innerHTML = "Oops! There was a problem. Please try again later. ";
	   }

	   // handle the form submission event

	   form.addEventListener("submit", function(ev) {
	     ev.preventDefault();
	     var data = new FormData(form);
	     ajax(form.method, form.action, data, success, error);
	   });
	 });
	 
	 // helper function for sending an AJAX request

	 function ajax(method, url, data, success, error) {
	   var xhr = new XMLHttpRequest();
	   xhr.open(method, url);
	   xhr.setRequestHeader("Accept", "application/json");
	   xhr.onreadystatechange = function() {
	     if (xhr.readyState !== XMLHttpRequest.DONE) return;
	     if (xhr.status === 200) {
	       success(xhr.response, xhr.responseType);
	     } else {
	       error(xhr.status, xhr.response, xhr.responseType);
	     }
	   };
	   xhr.send(data);
	 }
	</script>
