---
layout: page
title: Get in Touch
permalink: /contact/
---

<div class="contact-section" markdown="1">

<p>
  Request more information about outfitting your Outer Banks
  rental property.
</p>

<form
  id="contact-form"
  action="https://formspree.io/f/xppzpvnq"
  method="POST"
  class="contact-form"
>
  <label for="name">Name</label>
  <input type="text" id="name" name="name" required>

  <label for="email">Email</label>
  <input type="email" id="email" name="email" required>

  <label for="message">Message</label>
  <textarea id="message" name="message" required></textarea>

  <input
    type="hidden"
    name="_subject"
    value="New inquiry from Smart Homes OBX website"
  >
  <button type="submit">Send</button>
</form>

<p id="form-status" class="form-status" hidden></p>

<script>
  (function () {
    var form = document.getElementById("contact-form");
    var status = document.getElementById("form-status");

    function showStatus(message) {
      form.hidden = true;
      status.textContent = message;
      status.hidden = false;
    }

    form.addEventListener("submit", function (event) {
      event.preventDefault();

      fetch(form.action, {
        method: "POST",
        body: new FormData(form),
        headers: { Accept: "application/json" },
      })
        .then(function (response) {
          if (response.ok) {
            showStatus(
              "Thanks for reaching out. We'll get back to " +
                "you shortly."
            );
          } else {
            showStatus(
              "Something went wrong. Please try again, or " +
                "email info@SmartHomesOBX.com directly."
            );
          }
        })
        .catch(function () {
          showStatus(
            "Something went wrong. Please try again, or " +
              "email info@SmartHomesOBX.com directly."
          );
        });
    });
  })();
</script>

</div>
