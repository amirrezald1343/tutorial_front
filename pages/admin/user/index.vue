<template>
  <div>
    <v-card>
      <v-card-title>
        users controller
      </v-card-title>
      <v-card-text>
        <v-btn color="primary" @click="reload()">reload</v-btn>
        <UserTable ref="userTable"></UserTable>
      </v-card-text>
    </v-card>
  </div>

</template>

<script>
import UserTable from '@/components/User/UserTable'
export default {
  components:{
    UserTable
  },
  data:()=>({

  }),
  methods:{
    reload(){
      this.$refs.userTable.getUsers();
    }
  }
}
</script>
