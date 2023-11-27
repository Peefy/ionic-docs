```html
<template>
  <ion-page>
    <ion-list>
      <ion-item>
        <ion-input autofocus placeholder="with `autofocus`"></ion-input>
      </ion-item>
      <ion-item>
        <ion-input ref="input" placeholder="using `.setFocus()`"></ion-input>
      </ion-item>
    </ion-list>
  </ion-page>
</template>

<script lang="ts">
  import { IonInput, IonItem, IonList, IonPage, onIonViewDidEnter } from '@ionic/vue';
  import { ref } from 'vue';

  export default {
    components: { IonInput, IonItem, IonList, IonPage },
    setup() {
      const input = ref();
      onIonViewDidEnter(() => {
        requestAnimationFrame(() => {
          // We need requestAnimationFrame here because of
          // https://github.com/ionic-team/ionic-framework/issues/24434
          input.value.$el.setFocus();
        });
      });
      return { input };
    },
  };
</script>
```
