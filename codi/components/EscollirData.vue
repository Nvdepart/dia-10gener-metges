<template>
    <div v-if="metge">
        <h1>{{metge.nom}}</h1>
        <h3>{{metge.especialitat}}</h3>
        <v-date-picker v-model="dataSeleccionada">{{dataSeleccionada}}</v-date-picker>
        <v-text-field
            v-model="nomPatient"
            hide-details="auto"
            label="Full Name"
            placeholder="Nom"
            type="text"
        >Nom</v-text-field>
        <v-text-field
            v-model="emailPatient"
            hide-details="auto"
            label="Email address"
            placeholder="johndoe@gmail.com"
            type="email"
        >Email</v-text-field>
        <v-text-field
            v-model="telefonPatient"
            hide-details="auto"
            label="telefon"
            placeholder="600 00 00 00"
            type="telefon"
        >Telefon</v-text-field>
        <v-btn :disabled="isValidate" @click="submit()">Submit</v-btn>
        <v-btn :disabled="isValidate" @click="snackbar = true" color="green">Enviar</v-btn>
                <v-snackbar
                v-model="snackbar"
                
                >
                    <div class="text-subtitle-1 pb-2">la cita es : {{dataSeleccionada}}</div>
            
                    <p>El teu nom es: <Strong>{{nomPatient}}</Strong></p>
                    <p>El teu email es: <Strong>{{emailPatient}}</Strong></p>
                    <p>El teu telefon es: <Strong>{{telefonPatient}}</Strong></p>
            
                    <template v-slot:actions>
                    <v-btn
                        color="white"
                        variant="text"
                        @click="snackbar = false"
                    >
                    Close
                    </v-btn>
                </template>
            </v-snackbar>
        <p>{{nomPatient}} <br>{{emailPatient}} <br>{{telefonPatient}}</p>
    </div>
</template>

<script>
    export default {
        props:['metge'],
        data() {
            return {
                dataSeleccionada:"",
                nomPatient:"",
                emailPatient:"",
                telefonPatient:"600-00-00-00",
                snackbar: false,
            }
        },
        methods:{
            submit(){
                alert([
                   ['el Data de la cita es:', this.dataSeleccionada],
                    ["El teu Nom es",this.nomPatient],
                    ["El teu email es",this.emailPatient],
                    ["El teu telefon es",this.telefonPatient],
                ]
                    );
            },
            validar_email(email) {
            var regex = /^([a-zA-Z0-9_\.\-])+\@(([a-zA-Z0-9\-])+\.)+([a-zA-Z0-9]{2,4})+$/;
            return regex.test(email) ? true : false;
            }
        },
        computed:{
            isValidate(){
                if(
                        this.nomPatient != "" 
                        && this.emailPatient != "" 
                        && this.telefonPatient != "" 
                        && this.dataSeleccionada !=""
                 ) {return false }
                    
                    return true
            }
        }
    }
</script>

<style scoped>

</style>