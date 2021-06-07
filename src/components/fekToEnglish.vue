<template>
    
        <v-row class="mx-10"><v-sheet  class="mx-auto my-auto mt-4"
                        color="white"
                        elevation="0"
                        width="700"
        >
            <v-card-title>Fek</v-card-title>
            <v-textarea v-model="inputFek" background-color="accent" spellcheck="false" dark label="Type Fek here..." solo auto-grow></v-textarea>
        </v-sheet><v-sheet class="mx-auto my-auto mt-4"
                           color="white"
                           elevation="0"
                           width="700"
        >
            <v-card-title>English</v-card-title>
            <v-textarea label="English will appear here..." background-color="info" dark v-model="outputEnglish" readonly solo auto-grow></v-textarea>
        </v-sheet></v-row>
        
    
</template>

<script>
    export default {
        name: "fekToEnglish",
        data(){
            return {
                inputFek:"",
                wordMap:{
                    fek:"hello",
                    for:"one",
                    kon:"two",
                    goine:"three",
                    kataka:"four",
                    sin:"five",
                    u:"and",
                    e:"is",
                    egdi:"think",
                    noi:"I",
                    noien:"we",
                    ki:"you",
                    kien:"you all",
                    si:"he/she/it",
                    sien:"they/them",
                    yi:"yes",
                    ni:"no/not",
                    retwe:"water",
                    fshka:"use",
                    ren:"person",
                    renen:"people",
                    hakado:"in",
                    sinke:"made",
                    qua:"what",
                    quy:"why",
                    qu:"who",
                    quen:"where",
                    quo:"when",
                    hambre:"understand",
                    ambre:"don't understand",
                    hmm:"maybe",
                    sami:"because",
                    sofi:"therefore",
                    apuha:"help",
                    paer:"speak",
                    paert:"speak",
                    blom:"pencil",
                    zame:"money",
                    sovo:"cow"
                }
            }
        },
        methods:{
            fekToEnglish(fek){
                
                const broken = fek.split(" ");
                let out = [];
                for (let word of broken){
                    if (word.length===0){
                        continue
                    }
                    const firstUp = word[0].toUpperCase() === word[0];
                    const allUp = word.toUpperCase() === word;
                    const puncAtEnd = [".","!","?",","].includes(word[word.length-1]);
                    console.log(word, puncAtEnd);
                    const lastLetter = word[word.length-1];
                    if (puncAtEnd){
                        word = word.slice(0, word.length-1);
                    }
                    let newWord = this.wordMap[word.toLowerCase()];
                    if (newWord && allUp){
                        newWord = newWord.toUpperCase()
                    }
                    else if (newWord && firstUp){
                        newWord = newWord[0].toUpperCase() + newWord.slice(1)
                    }
                    if  (newWord && puncAtEnd){
                        newWord = newWord + lastLetter;
                    }
                    else if (puncAtEnd){
                        word = word + lastLetter
                    }
                    
                    out.push(newWord || word)
                }
                return out.join(" ")
            }
        },
        computed:{
            outputEnglish(){
                return this.fekToEnglish(this.inputFek)
            }
        }
    }
</script>

<style scoped>

</style>
