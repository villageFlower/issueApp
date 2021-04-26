<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Blank</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-select
        interface="popover"
        :value="selected"
        v-model="selected"
        @ionChange="selected = $event.target.value"
      >
        <ion-select-option value="iniValue"> Please Select</ion-select-option>
        <ion-select-option value="facilities">facilities</ion-select-option>
      </ion-select>
      <ion-select
        interface="popover"
        :value="selected"
        v-model="selected"
        @ionChange="onChange()"
      >
        <ion-select-option value="iniValue">Please Select</ion-select-option>
        <ion-select-option value="facilities">facilities</ion-select-option>
      </ion-select>
      <ion-text>here is the varable that binded to [:value] </ion-text>
      <ion-text style="color:red;">Expected Binding Value {selected} :{{selected}}</ion-text>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar,
} from "@ionic/vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "Home",
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
  },
  data() {
    return {
      selected: "iniValue",
    };
  },
  methods: {
    onChange() {
      console.log(this.selected);
    },
  },
});
</script>

<style scoped>
#container {
  text-align: center;

  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;

  color: #8c8c8c;

  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>