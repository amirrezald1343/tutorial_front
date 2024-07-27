<template>
  <v-col>
    <v-col cols="12">
      <ShowInformation :firstname="name" test="sdfsdf" @changeUser="testEmit"></ShowInformation>
    </v-col>
    <v-col cols="12">
      <h4>welcome to nuxt js learning : {{message}}</h4>
    </v-col>
    <v-col cols="12">
      <v-card>
        <v-card-title>
          <h4>show User info</h4>
        </v-card-title>
        <v-card-text>
          <v-text-field label="name" v-model="name" ></v-text-field>
<!--          <v-text-field label="name" v-model="color"></v-text-field>-->
        </v-card-text>
<!--        {{lastname}}<br>-->
<!--        {{age()}}<br>-->
<!--        {{color}}-->
<!--        {{classes}}-->
        <v-btn color="teal" @click="submitPage()">submit</v-btn>
      </v-card>
    </v-col>
  </v-col>
</template>

<script>
import ShowInformation from '@/components/User/ShowInformation.vue'
export default {
  components:{
    ShowInformation
  },
  data:()=>({
    name:'',
    classes:'',
    message:''
  }),
  mounted(){
    this.name = 'sdfsdf';
  },
  created(){

  },
  computed:{
    lastname(){
      return 'amirreza'
    },
    color:{
      get(){
        return this.name;
      },
      set(val){
        this.classes = val
      }
    }
  },
  methods:{
    age(){
      return 20
    },
    submitPage(){
      alert('submit page');
    },
    test(){
      this.submitPage();
    },
    testEmit(payloads){
      console.log(payloads);
      this.message = payloads
    }
  },
  watch:{
    name(value,before){
      console.log(value,before);
    }
  }
}
</script>
