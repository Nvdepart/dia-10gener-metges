<template>
    <v-container>
        <v-row>
            <v-col>
                <EscollirMetge
                @nou_metge_event="metgeEscollit"
                ></EscollirMetge>
            </v-col>
            <v-col>
                <EscollirData :metge="metgeSeleccionat"></EscollirData>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
    export default {
        data() {
            return {
                metgeSeleccionat : null
            }
        },
        methods:{
            metgeEscollit(metge){
                console.log("Parent", metge);
                this.metgeSeleccionat = metge
            }
        }
    }
</script>

<style scoped>

</style>