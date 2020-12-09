<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">INTEINGETE</div>

                    <div class="card-body">
                        <mesa></mesa>
                    </div>

                    {{datito}}
                </div>
            </div>
        </div>
    </div>
</template>

<script>

    import axios from 'axios';

    export default {
        data(){
            return {
                datito: []
            }
        },
        mounted() {
            console.log('Component mounted.')
        },
        created(){
            this.traerData();
        },
        methods: {
            async traerData() {
                console.log("mul");
                var link='https://jsonplaceholder.typicode.com/users';
                var Data = await axios.get(link);
                this.datito = Data;
                console.log(Data);
                // return Data;    
                
            }
        }
    }

    
</script>
