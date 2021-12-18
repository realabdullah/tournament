<template>
  <Navbar />
  <h2>Players Table</h2>
  <div class="table-wrapper">
    <table class="fl-table">
      <thead>
        <tr>
          <th>Name</th>
          <th>E-mail</th>
          <th>Phone</th>
          <th>Faculty</th>
          <th>Department</th>
          <th>Game</th>
          <th>COD Username</th>
          <th>Team Name</th>
          <th>UserID</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="player in players">
          <td>{{ player.name }}</td>
          <td>{{ player.email }}</td>
          <td>{{ player.phone }}</td>
          <td>{{ player.faculty }}</td>
          <td>{{ player.department }}</td>
          <td>{{ player.game }}</td>
          <td>
            <span v-if="player.cod_username">{{ player.cod_username }}</span>
            <span class="not" v-else>Not registered</span>
          </td>
          <td>
            <span v-if="player.team_name">{{ player.team_name }}</span>
            <span class="not" v-else>Not registered</span>
          </td>
          <td>
            <span v-if="player.userid">{{ player.userid }}</span>
            <span class="not" v-else>Not registered</span>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import Navbar from '../components/Navbar'
import { ref, onBeforeMount } from 'vue'
import { supabase } from '../supabase'

export default {
  components: {
    Navbar
  },
  setup() {
    const players = ref([])

    const getPlayers = async () => {
      try {  
        const data = await supabase
        .from('players')
        .select('*')
        players.value = data.data
      }
      catch(error) {

      }
    }

    onBeforeMount(() => {
      getPlayers()
    })

    return {
      players
    }
  }
}
</script>

<style scoped>
h2{
    text-align: center;
    font-size: 18px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: #324960;
    padding: 30px 0;
}

/* Table Styles */

.table-wrapper{
  margin: 10px 70px 70px;
  box-shadow: 0px 35px 50px rgba( 0, 0, 0, 0.2 );
  overflow: auto;
  text-align: left;
}

.fl-table {
  border-radius: 5px;
  font-size: 12px;
  font-weight: normal;
  border: none;
  border-collapse: collapse;
  width: 100%;
  max-width: 100%;
  white-space: nowrap;
  background-color: white;
}

.fl-table td, .fl-table th {
  text-align: center;
  padding: 8px;
}

.fl-table td {
  border-right: 1px solid #f8f8f8;
  font-size: 12px;
}

.fl-table thead th {
  color: #ffffff;
  background: #324960;
}

.fl-table tr:nth-child(even) {
  background: #F8F8F8;
}

.not {
  text-decoration: line-through;
  color: #324960;
  font-weight: 700;
}

/* Responsive */

@media (max-width: 767px) {
  .fl-table {
    display: block;
    width: 100%;
  }
  .table-wrapper:before{
    content: "Scroll horizontally >";
    display: block;
    text-align: right;
    font-size: 11px;
    color: white;
    padding: 0 0 10px;
  }
  .fl-table thead, .fl-table tbody, .fl-table thead th {
    display: block;
  }
  .fl-table thead th:last-child{
    border-bottom: none;
  }
  .fl-table thead {
    float: left;
  }
  .fl-table tbody {
    width: auto;
    position: relative;
    overflow-x: auto;
  }
  .fl-table td, .fl-table th {
    padding: 20px .625em .625em .625em;
    height: 60px;
    vertical-align: middle;
    box-sizing: border-box;
    overflow-x: hidden;
    overflow-y: auto;
    width: 120px;
    font-size: 13px;
    text-overflow: ellipsis;
  }
  .fl-table thead th {
    text-align: left;
    border-bottom: 1px solid #f7f7f9;
  }
  .fl-table tbody tr {
    display: table-cell;
  }
  .fl-table tbody tr:nth-child(odd) {
    background: none;
  }
  .fl-table tr:nth-child(even) {
    background: transparent;
  }
  .fl-table tr td:nth-child(odd) {
    background: #F8F8F8;
    border-right: 1px solid #E6E4E4;
  }
  .fl-table tr td:nth-child(even) {
    border-right: 1px solid #E6E4E4;
  }
  .fl-table tbody td {
    display: block;
    text-align: left;
  }
}
</style>