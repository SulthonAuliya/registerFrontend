<template>
    <div class="register">
        <div class="container">
            <div class="card">
                <div class="container">
                    <div class="title">
                        <h1 class="text-center mt-1">Register Now!</h1>
                    </div>
                    
                    <!-- form -->
                    <form action="" class="mt-5">
                        <div class="row">
                            <div class="col-md-12 col-lg-12 col-xl-6 form-group ">
                                <label for="first_name">First Name</label>
                                <input type="text" class="form-control" id="first_name" name="first_name" placeholder="First Name" required>
                            </div>

                            <div class="col-md-12 col-lg-12 col-xl-6 form-group ">
                                <label for="last_name">Last Name</label>
                                <input type="text" class="form-control" id="last_name" name="last_name" placeholder="Last Name" required>
                            </div>

                            <div class="col-md-12 col-lg-12 col-xl-6 form-group ">
                                <label for="email">Email</label>
                                <input type="email" class="form-control" id="email" name="email" placeholder="Email" required>
                            </div>

                            <div class="col-md-12 col-lg-12 col-xl-6 form-group ">
                                <label for="password">Password</label>
                                <input type="text" class="form-control" id="password" name="password" placeholder="Password" required>
                            </div>

                            <div class="col-lg-12 col-xl-4 form-group ">
                                <label for="jk">Jenis Kelamin</label>
                                <select class="form-control" name="jk" id="jk">
                                    <option value="">Laki-Laki</option>
                                </select>
                            </div>

                            <div class="col-lg-12 col-xl-4 form-group ">
                                <label for="provinsi">Provinsi</label>
                                <select v-model="selectedProvince" class="form-control" name="provinsi" id="provinsi" @change="selectProvince">
                                    <option v-for="(province, id_provinsi) in provinsi" :value="id_provinsi" :key="id_provinsi">
                                        {{province.name}}
                                    </option>
                                </select>
                            </div>

                            <div class="col-lg-12 col-xl-4 form-group ">
                                <label for="kota">Kota</label>
                                <select v-model="selecteditem" class="form-control" name="kota" id="kota">
                                    <option v-for="(city, id_city) in option" :key="id_city" >
                                        {{ city.nama }}
                                    </option>
                                </select>
                            </div>

                            <div class="col-lg-12 form-group mt-5">
                                <button class="btn btn-regis">Register</button>
                            </div>

                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            provinsi:[
                {
                    id: 1,
                    name: "Jawa Barat",
                    kota:[ 
                            {
                                id:1,
                                nama: "Bandung"
                            },
                            {
                                id: 2,
                                nama: "TasikMalaya"
                            },
                            {
                                id: 3,
                                nama: "Cirebon"
                            },
                            {
                                id: 4,
                                nama: "Depok"
                            },
                            {
                                id: 5,
                                nama: "Cimahi"
                            },
                        ]
                },

                {
                    id: 2,
                    name: "Jawa Timur",
                    kota:[ 
                            {
                                id: 1,
                                nama: "Jombang"
                            },
                            {
                                id: 2,
                                nama: "Surabaya"
                            },
                            {
                                id: 3,
                                nama: "Malang"
                            },
                            {
                                id: 4,
                                nama: "madiun"
                            },
                            {
                                id: 5,
                                nama: "Kediri"
                            },
                        ]
                }
            ],
            selectedProvince:-1,
            selecteditem:'',
            option:[]
        }
    },

    methods: {
        selectProvince:function(){
            this.selecteditem = '';
            this.option = this.provinsi[this.selectedProvince].kota;
        }
    }
}
</script>