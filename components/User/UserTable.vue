<template>
  <v-simple-table>
    <template v-slot:default>
      <thead>
      <tr>
        <th class="text-left">
          Name
        </th>
        <th class="text-left">
          created at
        </th>
        <th>
          operation
        </th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="item in users">
        <td>{{item.name}}</td>
        <td>{{item.created_at}}</td>
        <td><v-btn @click="getUserById(item.id)">operation</v-btn></td>
      </tr>
      </tbody>
    </template>
  </v-simple-table>
</template>


<script>
export default {
  inject:['showNotification'],
  data:()=>({
    users:[]
  }),
  mounted(){
    this.getUsers();
  },
  methods:{
    getUsers(){
      this.$axios.get('http://127.0.0.1:8000/api/get-users').then(res=>{
        this.users = res.data;
        this.showNotification("user list successfully ok");
      }).catch(error=>{
        this.getUsers();
        this.showNotification("500 error from server");
      })
    },
    getUserById(id){
      const data = {
        user_id : id
      }
      this.$axios.get('http://127.0.0.1:8000/api/get-user-by-id',{params:data}).then(res=>{
        this.showNotification(`user list successfully ok ${res.data.name}`);
      }).catch(error=>{
        this.showNotification("500 error from server");
      })
    }
  }
}
</script>
