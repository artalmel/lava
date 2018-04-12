<template>
  <div>
    <div class="sign-group" id="sign-group">
      <button class="tab-button active" @click="sign_in">Sign In</button>
      <span class="vertical-separator"></span>
      <button class="tab-button" @click="sign_up">Sign Up</button>
    </div>
    <div class="tab">
      <div>
        <div class="form-group bg-accent-light">
          <label for="email">E-Mail</label>
          <input id="email" name="email" type="email" required="required" class="input" data-vv-id="1"
                 aria-required="true" aria-invalid="true">
        </div>
        <span class="help is-danger" style="display:none;"></span>
        <div class="form-group bg-accent-light password-input">
          <label for="password">Password</label>
          <input id="password" type="password" name="password" required="required" class="col-md-10 input"
                 data-vv-id="2" aria-required="false" aria-invalid="false">
          <a href="#">
                  <span class="showpass" @click="change_pass"><span class="icon-eye"></span></span>
          </a>
        </div>
        <span class="help is-danger" style="display:none;"></span>
        <div id="birthday" class="form-group birth-sex" style="display: none">
          <div class="col-6 bg-accent-light in-birth-sex">
            <label>Date of Birth</label>
            <input type="text" required="required" class="col-md-10">
          </div>
          <div class="radios">
            <label for="male">
              <input id="male" type="radio" name="sex" value="1">
              <span class="icon-man"></span></label><label for="female">
            <input id="female" type="radio" name="sex" value="2">
            <span class="icon-woman"></span>
          </label>
          </div>
        </div>
      </div>
      <div id="form-footer" class="form-footer">
        <a href="#">{{form_footer}}</a>
      </div>
      <button type="submit" class="btn btn-sign" @click="submit">Sign In Now</button>
    </div>
  </div>
</template>

<script>

  var counter=0;
  var birthday;
  var form_footer;
  var sign_group;
  var pass;


  function is_active(e) {
    sign_group.childNodes.forEach(function (el) {
      el.classList.remove('active');
    });
    e.target.classList.add('active');
  }

  export default {
    name: "AppForm",
    data(){
      return {form_footer: 'FORGOT PASSWORD?'}

    },
    mounted(){
      birthday = document.querySelector('#birthday');
      sign_group = document.querySelector('#sign-group');
      form_footer = document.querySelector('#form-footer');
      pass = document.querySelector('#password');
    },

    methods: {
      sign_in: function (e) {
        is_active(e);
        birthday.style.display = 'none';
        form_footer.childNodes[0].textContent = 'FORGOT PASSWORD?';
        counter = 0;
      },

      sign_up: function (e) {
        is_active(e);
        counter = 1;
        form_footer.childNodes[0].textContent = 'ALREADY HAVE AN ACCOUNT?';
      },

      submit: function () {
        if(counter === 1){
          birthday.style.display = 'flex';
        }
      },

      change_pass: function () {
        if (pass.type === "password") {
          pass.type = "text";
        } else {
          pass.type = "password";
        }
      }

    }
  }

</script>

<style scoped>

</style>
