---
title: Contact
subtitle: Fill out the following form and we will contact you as soon as possible
comments: false
---

<textarea id="message"  form="contact" style="min-width:100%; min-height:200px"> </textarea>
<form id=contact
      accept-charset="UTF-8">
  <input id="email" type="email" placeholder="your email"/>
  <input id="name" type="text" placeholder="your name"/>
  <button type="submit">Send</button>
</form>
<div class="alert alert-success" role="alert" style="display:none;"><strong>Great!</strong> We have got your details and someone will be in touch.</div>
<script type="text/javascript">
    $(document).ready(function(){
        console.log("test0");
      $('#contact').submit(function(event) {
          event.preventDefault();
          console.log("test");
          console.log($('#message').val())
        $.ajax({
          dataType: "json",
          method: "POST",
          url: "//formspree.io/daniel.nielsen85@gmail.com",
          data: {
            message: $('#message').val(),
            email: $('#email').val(),
            _subject: "CrossProduct - Contact Form",
            name: $('#name').val()
          }
        }).done(function(data) {
          $('#contact').remove();
          $('.alert').fadeIn();
        });
        event.preventDefault();
      });
    });
    </script>