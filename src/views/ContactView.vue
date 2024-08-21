<script setup lang="ts"></script>

<template>
  <div id="contact" ref="contact" class="contact_container">
    <div class="contact_body">
      <div class="form_description">
        <h2>Let's connect</h2>
        <br />
        <div class="desc_text">
          <p style="color: white; font-family: Deuterium">
            I’m here to bring your vision to life. <br /><br />
            Whether you’re inquiring for a few questions, or you’re ready to start your next big
            project, I’d love to meet and hear from you.
          </p>
          <br />
          <p style="color: white; font-family: Deuterium">
            Have a specific inquiry or want to request a quote?<br />
            Fill out the form, and I will get back to you as soon as possible.
          </p>
        </div>
      </div>
      <div class="contact_form">
        <form target="_blank" action="https://formsubmit.co/vjctoriaa@gmail.com" method="POST">
          <div style="display: flex; flex-direction: column; gap: 20px">
            <input type="text" name="name" placeholder="Full Name" required />
            <input type="email" name="email" placeholder="Email Address" required />
            <textarea placeholder="Your Message" name="message" rows="10" required></textarea>
          </div>
          <button type="submit" class="submit">Submit</button>
        </form>
      </div>
    </div>
  </div>
</template>

<style>
form {
  box-sizing: border-box;
  font-family: 'Manrope';

  input {
    background-color: #212121;
    border-radius: 2px;
    border: 0;
    color: #eee;
    font-size: 18px;
    height: 30px;
    outline: 0;
    padding: 10px;
    font-family: 'Manrope';
  }

  .submit {
    background-color: #525252;
    border-radius: 12px;
    border: 0;
    box-sizing: border-box;
    color: #eee;
    cursor: pointer;
    font-size: 18px;
    height: 50px;
    margin-top: 38px;
    text-align: center;
    width: 100%;
  }

  .submit:hover {
    background-color: #08d;
  }

  textarea {
    background-color: #212121;
    border-radius: 2px;
    border: 0;
    box-sizing: border-box;
    color: #eee;
    font-size: 18px;
    outline: 0;
    padding: 4px 20px 0;
    resize: none;
    font-family: 'Manrope';
  }

  .submit:active {
    background-color: #06b;
  }
}

.contact_container {
  height: 100vh;
  width: 100%;
  padding-top: 10%;
  padding-left: 15%;
  padding-right: 15%;
  animation: fadeInAnimation ease 1s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
}

.contact_body {
  display: flex;
  flex-direction: row;
}

.form_description {
  width: 55%;

  h2 {
    font-family: Deuterium;
    font-weight: 500;
    text-align: left;
    font-size: 70px;
  }

  .desc_text {
    padding-left: 30px;
    padding-right: 100px;
  }
}

.contact_form {
  width: 40%;
  margin-bottom: 0px;
}

@media screen and (max-width: 767px) {
  .contact_container {
    padding-left: 20px;
    padding-right: 20px;
  }
  .contact_body {
    flex-direction: column;
    gap: 40px;
  }

  .form_description {
    width: 100%;
    height: auto;
    h2 {
      text-align: center;
      font-size: 45px;
    }

    .desc_text {
      padding-left: 20px;
      padding-right: 20px;
      font-size: 20px;
    }
  }

  .contact_form {
    width: 100%;
    margin-bottom: 50px;
  }
}
</style>
