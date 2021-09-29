<template>
    <div id="app">
        <!-- As a heading -->
        <nav class="navbar navbar-dark bg-primary">
            <div class="container">
                <span class="navbar-brand mb-0 h1">Zakirsoft</span>
            </div>
        </nav>
        <section class="py-5">
            <div class="container">
                <!-- <h2 v-if="show">{{ message }}</h2>
                <p v-else class="text-danger">nothing found</p>

                <form action="" class="mt-3" @submit.prevent="showMessage">
                    <div class="form-group">
                        <label for="">Message </label>
                        <input type="text" class="form-control" v-model="message">
                    </div>
                    <button class="btn btn-primary" type="submit"> Show Message </button>
                </form> -->
                <form action="" class="py-3" @submit.prevent="storeStudentInfo()">
                    <div class="row">
                        <div class="col">
                            <input type="text" class="form-control" placeholder="Name" v-model="studentForm.name">
                        </div>
                        <div class="col">
                            <input type="text" class="form-control" placeholder="Roll" v-model="studentForm.roll">
                        </div>
                        <div class="col">
                            <button type="submit" class="btn btn-success">Add Student</button>
                        </div>
                    </div>
                </form>
                <h2>Student List</h2>
                <table class="table">
                    <thead class=" table-primary">
                        <tr>
                            <th> # </th>
                            <th> Name </th>
                            <th> Roll </th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="(student, index) in studentList" :key="index">
                            <td> {{ index }} </td>
                            <td> {{ student.name }} </td>
                            <td> {{ student.roll }} </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>
    </div>
</template>

<script>
export default {
  name: 'App',
  components: {
      
  },
  data() {
      return {
        //   message: '',
        //   show: false
        studentList: [
            {
                name: "Monir Uddin",
                roll: 1,
            },
            {
                name: "Jihad Hossain",
                roll: 2,
            },
            {
                name: "Mahedi Hasan",
                roll: 3,
            },
        ],
        // studentName: '',
        // StudentRoll: ''
        studentForm: {
            name: '',
            roll: null,
        }
      }
  },
  methods: {
    //   showMessage() {
    //       if(this.message == ""){
    //           alert('Please write something');
    //       }else {
    //           if(this.message == 10){
    //               this.show = true;
    //           }else {
    //               this.show = false;
    //           }
    //       }
    //   },
    storeStudentInfo() {
        console.log(this.studentForm);
        this.studentList.push(this.studentForm);
    }
  }
}
</script>

<style lang="scss">
    @import '~bootstrap/dist/css/bootstrap.min.css';
</style>
