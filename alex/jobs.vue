<template>
  <section>
    <section class="hero is-primary">
      <div class="hero-body">
        <div class="container">
          <p class="title">Industry Job Opportunites</p>
          <p class="subtitle">Below is a table of open positions and their requirements.</p>
        </div>
      </div>
    </section>
    <section class="joblist">
      <section class="section">
        <div class="container">
          <div v-if="!this.$auth.$storage.getCookie('member')">
            <div class="content">
              <p> UBIC Opportunities, internships, and job postings are only avaliable to UBIC members. If you'd like to become a member, please contant a member of UBIC board. </p>
            </div>
          </div>
          <div v-else>
            <table class="table is-responsive">
              <tr>
                <th>Company</th>
                <th>Title</th>
              </tr>
              <tr>
                <th>Grail</th>
                <th>SWE Intern</th>
              </tr>
            </table>
          </div>
        </div>
      </section>
    </section>
  </section>
</template>

<script>
import { db } from '../plugins/firebase'
//import JobRow from '../components/JobRow.vue'

export default {
  name: 'jobs',
  data () {
    return {
      jobs: [],
    }
  },
  
  firestore () {
    return {
      jobs: db.collection('jobs')
    }
  }
}
</script>


<style lang="scss" scoped>

</style>








<!-- .is-responsive {
  width: 100%;
  border-collapse: collapse;
  border-spacing: 0;
  display: block;
  position: relative;

  td:empty:before{
    content: "\00a0";
  }

  th {
    td {
      margin: 0;
      vertical-align: top;
    }
  }

  th {
    text-align: left;
  }

  thead {
    border-right: solid 2px;
    display: block;
    float: left;

    tr {
      display: block;
      padding: 0 10px 0 0;

      th::before{
        content: "\00a0";
      }
    }
    td {
      th {
        border-width: 0 0 1px;
      }
    }
  }
  tbody {
    display: block;
    width: auto;
    position: relative;
    overflow-x: auto;
    white-space: nowrap;

    tr {
      display: inline-block;
      vertical-align: top;
    }
  }

  th {
    display: block;
    text-align: right;
  }

  td {
    display: block;
    min-height: 1.25em;
    text-align: left;
  }

  th {
    td {
      last-child {
        border-bottom-width: 0;
      }
    }

    tr {
      last-child{
        td {
          
          border: table-cell-border;
          border-width: table-cell-border-width;
        }
      }
    }
  }
} -->