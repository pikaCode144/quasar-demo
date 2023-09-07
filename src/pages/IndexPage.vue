<template>
  <!-- <q-page class="flex flex-center">
    <img
      alt="Quasar logo"
      src="~assets/quasar-logo-vertical.svg"
      style="width: 200px; height: 200px"
    >
  </q-page> -->
  <div class="q-pa-none q-gutter-xl">
    <q-btn
      color="white"
      text-color="black"
      label="Standard"
      @click="openDialog"
    />
    <q-btn color="primary" label="Primary" />
    <q-btn color="secondary" label="Secondary" />
    <q-btn color="amber" glossy label="Amber" />
    <q-btn color="brown-5" label="Brown 5" />
    <q-btn color="deep-orange" glossy label="Deep Orange" />
    <q-btn color="purple" label="Purple" />
    <q-btn color="black" label="Black" />
  </div>
  <transition
    appear
    enter-active-class="animated fadeIn"
    leave-active-class="animated fadeOut"
  >
    <!-- Wrapping only one DOM element, defined by QBtn -->
    <q-btn color="secondary" icon="mail" label="Email" />
  </transition>
  <div class="row justify-between">
    <div>First column</div>
    <div>Second column</div>
    <div>Third column</div>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "IndexPage",
  mounted() {
    console.log(this.$q);
  },
  methods: {
    openDialog() {
      this.$q
        .dialog({
          title: "Alert",
          message: "Some message",
        })
        .onOk(() => {
          // console.log('OK')
        })
        .onCancel(() => {
          // console.log('Cancel')
        })
        .onDismiss(() => {
          // console.log('I am triggered on both OK and Cancel')
        });
    },
  },
});
</script>
