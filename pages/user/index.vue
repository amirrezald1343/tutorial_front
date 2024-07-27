<template>
  <v-card>
    <v-card-title color="blue">
      <h4>sdfsdf</h4>
    </v-card-title>
    <v-card-text>
      <v-row>
        <v-col cols="6">
          <v-text-field label="name"></v-text-field>
        </v-col>
        <v-col cols="6">
          <v-text-field label="name"></v-text-field>
        </v-col>
        <v-col cols="6">
          <v-text-field label="name"></v-text-field>
        </v-col>
        <v-col cols="6">
          <v-text-field label="name"></v-text-field>
        </v-col>
      </v-row>
    </v-card-text>
    <v-card-actions>
      <v-btn color="blue">click</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
import custom_input from '@/components/custom_input';

export default {
  middleware:['auth-check'],
  components:{
    ci:custom_input,
  },
  data(){
    return{
      name:'',
      lastname:'sfs',
      data:[],
      test:{
        title:'sdf'
      }
    }
  }
}
</script>

