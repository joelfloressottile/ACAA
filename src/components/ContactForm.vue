<template>
  <div class="contact">
    <p
      class="text-center"
    >Déjanos tus preguntas e inquietudes. Intentaremos responderte lo antes posible</p>
    <form @submit.prevent="checkForm" class="contact-form mt-4" method="post">
      <div class="m-0-auto mb-2 input-container">
        <label class="form-label text-left d-block mb-05">Tu nombre</label>
        <input type="text" class="form-input w-90" v-model.trim="$v.contactForm.firstName.$model" :class="{'input-has-error': $v.contactForm.firstName.$invalid && $v.contactForm.firstName.$dirty}"/>
      </div>
      <div class="m-0-auto mb-2 input-container">
        <label class="form-label text-left d-block mb-05">Tu apellido</label>
        <input type="text" class="form-input w-90" v-model.trim="$v.contactForm.lastName.$model" :class="{'input-has-error': $v.contactForm.lastName.$invalid && $v.contactForm.lastName.$dirty}"/>
      </div>
      <div class="m-0-auto mb-2 input-container">
        <label class="form-label text-left d-block mb-05">Tu correo</label>
        <input type="text" class="form-input w-90" v-model.trim="$v.contactForm.email.$model" :class="{'input-has-error': $v.contactForm.email.$invalid && $v.contactForm.email.$dirty}"/>
      </div>
      <!-- <div class="m-0-auto mb-2 input-container">
        <label class="form-label text-left d-block mb-05">Tu número de teléfono</label>
        <input type="text" class="form-input w-90" v-model="contactForm.phone" />
      </div>-->
      <div class="m-0-auto mb-2 input-container">
        <label class="form-label text-left d-block mb-05">Tu pregunta</label>
        <textarea
          placeholder="Escríbenos cualquier duda"
          class="form-input w-90 textarea"
          v-model.trim="$v.contactForm.message.$model" :class="{'input-has-error': $v.contactForm.message.$invalid && $v.contactForm.message.$dirty}"
        />
      </div>
      <div class="text-center">
        <button class="primary-btn no-shadow send-button" :disabled="this.$v.$invalid">{{ !this.$v.$invalid ? 'Enviar mensaje' : 'Enviar mensaje (faltan datos)'}}</button>
      </div>
    </form>
  </div>
</template>

<script>
import {
  required,
  email,
  minLength,
  maxLength,
} from "vuelidate/lib/validators";
export default {
  data() {
    return {
      contactForm: {
        firstName: "",
        lastName: "",
        email: "",
        // phone: "",
        message: ""
      }
    };
  },
  validations: {
    contactForm: {
      firstName: {
        required
      },
      lastName: {
        required
      },
      email: {
        required,
        email
      },
      message: {
        required,
        maxLength: maxLength(300)
      }
    }
  },
  methods: {
    checkForm() {
      this.$v.$touch();

      if (!this.$v.$invalid) {
        console.log("Valid form");
        this.sendMessage();
      } else {
        console.log("Invalid form");
      }
    },
    sendMessage(){
      console.log('Message sent');
      this.clearForm();
      this.$v.$reset();
    },
    clearForm(){
      this.contactForm = {
        firstName: "",
        lastName: "",
        email: "",
        message: ""
      }
    }
  }
};
</script>

<style scoped>
.input-container {
  width: 90%;
  min-width: 300px;
}

.send-button {
  width: 90%;
}

.textarea {
  height: 80px;
}

@media only screen and (min-width: 600px) {
  .input-container {
    width: 40%;
  }

  .send-button {
    width: auto;
  }
}
</style>
