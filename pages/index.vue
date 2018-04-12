<template>
    <div class="d-flex">
      <div class="container">
        <header>
          <app-demo/>
        </header>
        <div class="row">
        <div class="col-lg-6 col-xl-4">
          <h1>Welcome <span>to LAVA</span></h1>
          <div id="tabs">
            <app-form/>
            <div>
              <div class="separate"><span>or</span>
              </div>
            <app-facebook/>

            </div>
          </div>
        </div>
        <div class="col-lg-6 col-xl-8">
          <img src="/img/demo.c47efac.png" alt="" class="w-100">
        </div>
      </div>
      </div>

    </div>

</template>


<script>


  import AppForm from '~/components/AppForm.vue';
  import AppDemo from '~/components/AppDemo.vue';
  import AppFacebook from '~/components/AppFacebook.vue';

export default {
  components: {
    AppForm,
    AppDemo,
    AppFacebook
  },

}


</script>


