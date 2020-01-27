<template>
  <div class="container">
    <div class="card p-3 m-5 rounded">
      <h3 class="card-header mb-3">Enter your phone</h3>
      <form class="d-flex">
        <div :class="['sinFlag', getFondo(),'btn']" @click="showModal('', '')"></div>
        <div class="select" @click="showModal('', '')"></div>

        <input
          v-model="prefijo"
          class="form-group p-1 h6"
          type="text"
          placeholder="Your phone number here"
        />
      </form>
    </div>
    <!-- Modal flag window  -->
    <div v-if="modal" class="card w-modal rounded animated fadeIn fast">
      <h6 class="card-header text-center h4">Choose your country</h6>
      <div class="card-body">
        <ul class="list-group list-group-flush">
          <li class="list-group-item list-group-item-action btn">
            <a @click="showModal('+353', 'ireland')">
              <h6>
                <img class="mr-3" src="../assets/ireland.png" width="40px" />+353 Ireland
              </h6>
            </a>
          </li>
          <li class="list-group-item list-group-item-action btn">
            <a @click="showModal('+34', 'spain')">
              <h6>
                <img class="mr-3" src="../assets/spain.png" width="40px" />+34 Spain
              </h6>
            </a>
          </li>
          <li class="list-group-item list-group-item-action btn">
            <a @click="showModal('+33', 'france')">
              <h6>
                <img class="mr-3" src="../assets/france.png" width="40px" />+33 France
              </h6>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "VuePhoneNumber",
  data() {
    return {
      phone: "Phone number",
      modal: false,
      prefijo: "",
      flagActual: "sinFlag"
    };
  },
  methods: {
    showModal(country_code, country_name) {
      this.prefijo = country_code;
      this.modal = !this.modal;
      this.flagActual = country_name;
    },
    getFondo() {
      return this.flagActual; // Return the bg
    }
  }
};
</script>
<style>
.card {
  margin: 0 auto;
  float: none;
}
.w-modal {
  width: 30%;
}
.a:hover {
  cursor: pointer;
}
.sinFlag,
.spain,
.ireland,
.france {
  background-size: 40px;
  width: 40px;
  background-repeat: no-repeat;
}
.sinFlag {
  background-image: url("../assets/no_country.jpg");
}
.spain {
  background-image: url("../assets/spain.png");
}
.france {
  background-image: url("../assets/france.png");
}
.ireland {
  background-image: url("../assets/ireland.png");
}
.select {
  background-size: 30px;
  width: 30px;
  background-repeat: no-repeat;
  background-image: url("../assets/select.png");
}
/* ANIMATED CSS FOR THE MODAL */
.animated {
  -webkit-animation-duration: 1s;
  animation-duration: 1s;
  -webkit-animation-fill-mode: both;
  animation-fill-mode: both;
}

.fast {
  -webkit-animation-duration: 0.6s;
  animation-duration: 0.6s;
  -webkit-animation-fill-mode: both;
  animation-fill-mode: both;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

.fadeIn {
  animation-name: fadeIn;
}
</style>
