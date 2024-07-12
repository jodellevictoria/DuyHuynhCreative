<script setup lang="ts"></script>

<template>
  <div
    id="contact"
    ref="contact"
    style="
      height: 100vh;
      width: 100%;
      padding-top: 90px;
      padding-left: 50px;
      animation: fadeInAnimation ease 1s;
      animation-iteration-count: 1;
      animation-fill-mode: forwards;
    "
  >
    <h2>Contact</h2>
    <div style="display: flex">
      <div style="width: 60%; padding: 30px">
        <h3 style="color: white; font-size: 50px">Fill the form to contact</h3>
        <p style="color: white">
          Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has
          been the industry's standard dummy text ever since the 1500s, when an unknown printer took
          a galley of type and scrambled it to make a type specimen book. It has survived not only
          five centuries, but also the leap into electronic typesetting, remaining essentially
          unchanged. It was popularised in the 1960s
        </p>
      </div>
      <div>
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
  width: 400px;

  input {
    background-color: #212121;
    border-radius: 2px;
    border: 0;
    color: #eee;
    font-size: 18px;
    height: 24px;
    outline: 0;
    padding: 10px;
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
    font-family:
      Inter,
      -apple-system,
      BlinkMacSystemFont,
      'Segoe UI',
      Roboto,
      Oxygen,
      Ubuntu,
      Cantarell,
      'Fira Sans',
      'Droid Sans',
      'Helvetica Neue',
      sans-serif;
  }

  .submit:active {
    background-color: #06b;
  }
}
</style>
