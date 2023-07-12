<template>
  <div class="app-container">
    <DxButton
      :width="120"
      text="ShowPopup"
      type="success"
      styling-mode="outlined"
      @click="showPopup"
    />
    <DxPopup :visible="popupVisible" :hide-on-outside-click="false" :show-close-button="false" container=".app-container" height="80%" width="80%"
        title="Search">
        <DxPosition
            my="center"
            at="center"
            of=".app-container"
        />
        <DxButton
          :width="120"
          text="HidePopup"
          type="success"
          styling-mode="outlined"
          @click="hidePopup"
        />
      </DxPopup>
  </div>
</template>

<script setup name="Profile">
import DxButton from 'devextreme-vue/button';
import { DxPopup,DxPosition } from 'devextreme-vue/popup';
import {ref,onActivated, onDeactivated,onMounted} from 'vue'

const popupVisible = ref(true)

function showPopup(){
  console.log('showPopup',popupVisible.value)
  popupVisible.value = true
}

function hidePopup(){
  console.log('hidePopup',popupVisible.value)
  popupVisible.value = false
}

onActivated(()=>{
  console.log('onActivated')
})

onDeactivated(()=>{
  console.log('onDeactivated')
})

onMounted(() => {
  console.log('onMounted')
});

</script>

<style lang="scss">
.app-container{
  flex: auto;
}
</style>
