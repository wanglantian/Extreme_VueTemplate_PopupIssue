<template>
  <div class="app-container">
    <DxDataGrid
    :data-source="arr"
    :columns="columns"
    :show-borders="true"
    height="500px"
    style="padding:50px"
  />
  </div>
</template>

<script setup name="Profile">
import DxDataGrid from 'devextreme-vue/data-grid';

import {onActivated, onDeactivated,onMounted} from 'vue'


let columns = [];
let arr = [];
for(let i=0;i<20;i++){
  let columnName = 'column' + i;
  columns.push(columnName);
  for(let j = 0;j<20;j++){
    if(!arr[j]) arr[j] = {};
    arr[j][columnName] = j;
  }
}



onActivated(()=>{

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
