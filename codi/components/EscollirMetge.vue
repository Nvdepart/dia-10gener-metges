<template>
    <div>
        <v-card>
            <v-card-title>
                Lista de metges
            </v-card-title>
            <br>
            <v-card-title 
                class="metge" 
                @click="selleccionarMetge(pos)"
                v-for="(metge, pos) in metges" 
                :keys="pos" 
                >
                
                <pre>
                    <strong>{{ metge.nom }}</strong>
                    {{ metge.especialitat }}
                </pre>
             
            </v-card-title>
        </v-card>
    </div>
</template>

<script>
import 'bulma/css/bulma.css'

export default {
    data(){
        return{
            metges:[
                {
                    nom:"Dr.Tal",
                    especialitat:"Traumatologie"
                },
                {
                    nom:"Dr.R",
                    especialitat:"Medico General"
                },
                {
                    nom:"Dr.D",
                    especialitat:"Traumatologie"
                },
                {
                    nom:"Dr.C",
                    especialitat:"Medico General"
                },
            ]
            }
        },
        methods:{
            selleccionarMetge(element){
                {
                    console.log("Metge seleccionat", this.metges[element])
                    this.$emit('nou_metge_event', this.metges[pos])
                }
            }
        }
    }

</script>

<style scoped>
.metge{
    background-color: rgb(174, 185, 207);
    margin: 5px;
    padding: 5px;
    cursor: pointer;
}
</style>