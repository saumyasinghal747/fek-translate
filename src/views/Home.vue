<template>
  <div class="home">
    
    <fek-to-english/>
    <v-row class="mt-4 ml-16 pl-5">
      <v-col><h1 >Qua e "Fek"?</h1>
        <br/>
        <p>Noien sinke Fek. Noien paert Fek. ..... [Qua]</p></v-col>
      
    </v-row>
  </div>
</template>

<script>
// @ is an alias to /src

import FekToEnglish from "@/components/fekToEnglish";

export default {
  name: 'Home',
  components: {
    FekToEnglish
  }
}
</script>
