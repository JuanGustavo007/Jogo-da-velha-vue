<template>
    
    <p class="velha">Jogo da velha</p>
    <button class="btn btn-primary" @click="mostrarTabuleiro">{{resetar ? 'Remover tabuleiro' : 'Mostrar Jogo'}}</button>
        <div class="jogo" v-if="resetar">
            <div>
                <input type="text" class="p1" v-model="p1" @keyup.x.o="valores" maxlength="1" data-bs-toggle="tooltip" data-bs-html="true" title="Digite 'X' ou 'O'">
                <input type="text" class="p2" v-model="p2" @keyup.x.o="valores" maxlength="1" data-bs-toggle="tooltip" data-bs-html="true" title="Digite 'X' ou 'O'">
                <input type="text" class="p3" v-model="p3" @keyup.x.o="valores" maxlength="1" data-bs-toggle="tooltip" data-bs-html="true" title="Digite 'X' ou 'O'">
            </div>
            <div>
                <input type="text" class="p4" v-model="p4" @keyup.x.o="valores" maxlength="1" data-bs-toggle="tooltip" data-bs-html="true" title="Digite 'X' ou 'O'">
                <input type="text" class="p5" v-model="p5" @keyup.x.o="valores" maxlength="1" data-bs-toggle="tooltip" data-bs-html="true" title="Digite 'X' ou 'O'">
                <input type="text" class="p6" v-model="p6" @keyup.x.o="valores" maxlength="1" data-bs-toggle="tooltip" data-bs-html="true" title="Digite 'X' ou 'O'">
            </div>
            <div>
                <input type="text" class="p7" v-model="p7" @keyup.x.o="valores" maxlength="1" data-bs-toggle="tooltip" data-bs-html="true" title="Digite 'X' ou 'O'">
                <input type="text" class="p8" v-model="p8" @keyup.x.o="valores" maxlength="1" data-bs-toggle="tooltip" data-bs-html="true" title="Digite 'X' ou 'O'">
                <input type="text" class="p9" v-model="p9" @keyup.x.o="valores" maxlength="1" data-bs-toggle="tooltip" data-bs-html="true" title="Digite 'X' ou 'O'">
            </div>
            <p class="ganhador"> Quem ganho esse jogo foi: <span> {{qmGanho}} </span> </p>
        </div>
</template>


<script>

export default{
    name:'Jogo',
    data() {
        return {
            p1:'',
            p2:'',
            p3:'',
            p4:'',
            p5:'',
            p6:'',
            p7:'',
            p8:'',
            p9:'',
            qmGanho:'',
            resetar:false 
        }
    },
    methods:{
        mostrarTabuleiro(){
            this.resetar = !this.resetar
        }
    },
    computed:{
        valores(){
            //Condicoes da posicao p1
            if (this.p1.length > 0 && this.p1 ===this.p2 && this.p1 === this.p3){
                this.qmGanho = this.p1         
            }else if (this.p1.length > 0 && this.p1 ===this.p5 && this.p1 === this.p9){
                this.qmGanho = this.p1
            }else if (this.p1.length > 0 && this.p1 ===this.p4 && this.p1 === this.p7){
                this.qmGanho = this.p1
            }else if (this.p2.length > 0 && this.p2 === this.p5 && this.p2 === this.p8){
                this.qmGanho = this.p2
            }else if (this.p3.length > 0 && this.p3 === this.p5 && this.p3 === this.p7){
                this.qmGanho = this.p3
            }else if (this.p3.length > 0 && this.p3 ===this.p6 && this.p3 === this.p9){
                this.qmGanho = this.p3
            }else if (this.p4.length > 0 && this.p4 === this.p5 && this.p4 ===this.p6 ){
                this.qmGanho = this.p4
            }else if (this.p7.length > 0 && this.p7 === this.p8 && this.p7 === this.p9){
                this.qmGanho = this.p7
            }
        }

    },
    watch:{
        p1(){
            if (this.p1 !=='x' && this.p1 !== 'o'){
                this.p1 = ''
            }

        },
        p2(){
            if (this.p2 !=='x' && this.p2 !== 'o'){
                this.p2 = ''
            }

        },
        p3(){
            if (this.p3 !=='x' && this.p3 !== 'o'){
                this.p3 = ''
            }

        },
        p4(){
            if (this.p4 !=='x' && this.p4 !== 'o'){
                this.p4 = ''
            }

        },
        p5(){
            if (this.p5 !=='x' && this.p5 !== 'o'){
                this.p5 = ''
            }

        },
        p6(){
            if (this.p6 !=='x' && this.p6 !== 'o'){
                this.p6 = ''
            }

        },
        p7(){
            if (this.p7 !=='x' && this.p7 !== 'o'){
                this.p7 = ''
            }

        },
        p8(){
            if (this.p8 !=='x' && this.p8 !== 'o'){
                this.p8 = ''
            }

        },
        p9(){
            if (this.p9 !=='x' && this.p9 !== 'o'){
                this.p9 = ''
            }

        },

    }

}

</script>


<style scoped>

input{
    padding: 40px;
    text-align: center;
    border: none;
    outline: none;
}
.jogo{
    margin-top: 20px;
}
.p1{
    border-right: 2px solid black;
    border-bottom: 2px solid black;
}
.p2{
    border-bottom: 2px solid black;
    border-right: 2px solid black;

}
.p3{
    border-bottom: 2px solid black;
}
.p4{
    border-right: 2px solid black;
    border-bottom: 2px solid black;
}
.p5{
    border-bottom: 2px solid black ;
    border-right: 2px solid black;
}
.p6{
    border-bottom: 2px solid black;
}
.p7{
    border-right:2px solid black;
}
.p8{
    border-right: 2px solid black;
}
p:last-child{
    margin-top: 200px;
    text-align: center;
}
span{
    background-color: green;
    color: black;
    padding: 10px 10px;
}

input{
    font-size: 2rem;
}
.red {
    background-color: red;
}
.jogo input{
    background-color: rgb(252, 246, 238);
}
.velha {
    margin-bottom: 100px;
}

</style>>




