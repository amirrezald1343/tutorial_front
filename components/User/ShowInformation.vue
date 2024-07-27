<template>
  <v-card>
    <v-card-title>
      <h4>show User info</h4>
    </v-card-title>
    <v-card-text>
      <p>name : {{ firstname }} , lastname : sharifi</p>
    </v-card-text>
    <v-card-actions>
      <v-btn color="red darken-4" @click="destroy()">destroy</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  // props:['firstname'],
  props:{
    firstname:{
      default:'none name',
      required: true
    }
  },
  methods:{
    destroy(){
      this.$emit('changeUser',{
        name:'amirreza',
        lastname:'sharifi'
      })
      // this.$emit('destroyUser','amirreza')
    }
  }
}

</script>
