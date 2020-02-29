<template>
    <div class="container my-5 text-center justify-content-center">
        <div class="row">
            <div class="col-md-12">
                <h3>
                    JS String Manipulation
                </h3>
                <h5>
                    {{ description }}
                </h5>
                <h5>
                    <a target="_blank" href="https://github.com/ric-ez/js-string-manipulation">Source</a>
                </h5>
            </div>
        </div>

        <div class="row justify-content-center">
            <div class="col-md-6">
                <div class="form-group">
                    <textarea placeholder="hello_world" v-model="words" cols="30" rows="2" class="form-control" style="font-size: 30px;"></textarea>
                </div>
            </div>
        </div>

        <div class="row justify-content-center mb-4">
            <div class="col-md-6">
                <button @click="changeType('voweltoi', 'Vowel to i')" v-bind:class="[type === 'voweltoi' ? 'btn-primary' : 'btn-outline-primary']" class="btn mx-1 font-weight-bold my-1" style="letter-spacing: 2px;">
                    hilli_wirld
                </button>
                <button @click="changeType('voweltow', 'Vowel to w & y to i')" v-bind:class="[type === 'voweltow' ? 'btn-primary' : 'btn-outline-primary']" class="btn mx-1 font-weight-bold my-1" style="letter-spacing: 2px;">
                    hwllw_wwrld
                </button>
                <button @click="changeType('voweltonum', 'Vowel to number')" v-bind:class="[type === 'voweltonum' ? 'btn-primary' : 'btn-outline-primary']" class="btn mx-1 font-weight-bold my-1" style="letter-spacing: 2px;">
                    h3ll0_w0rld
                </button>
                <button @click="changeType('weirdword', 'wEiRD wOrD gEnErAtOr')" v-bind:class="[type === 'weirdword' ? 'btn-primary' : 'btn-outline-primary']" class="btn mx-1 font-weight-bold my-1" style="letter-spacing: 2px;">
                    hElLo_wOrLd
                </button>
            </div>
        </div>

        <div class="row justify-content-center" style="font-size: 30px;">
            <div class="col-md-6">
                <div class="card">
                    <div class="card-header text-center">
                        <div>Generate</div>
                        <button data-clipboard-target="#voweltoi" class="btn btn-outline-success btn-sm font-weight-bold">
                            Copy
                        </button>
                    </div>
                    <!-- <div class="form-group card-body"> -->
                        <textarea placeholder="hilli_wirld" id="voweltoi" v-model="this.generated" cols="30" rows="2" class="form-control" style="font-size: 30px;"></textarea>
                    <!-- </div> -->
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            type: 'voweltoi', 
            description: 'Vowel to i', 
            words: ''
        }
    }, 
    methods: {
        changeType(type, description){
            this.type = type
            this.description = description
        }
    },
    computed: {
        generated(){
            let res
            switch (this.type) {
                case 'voweltoi':
                    res = this.words.replace(/a|i|u|e|o/gi, 'i');
                    break;
                case 'voweltow':
                    res = 
                    this.words
                    .replace(/i/gi, 'y')
                    .replace(/e/gi, 'w')
                    .replace(/o/gi, 'w')
                    .replace(/a/gi, 'w')
                    .replace(/u/gi, 'w')
                    break;
                case 'voweltonum':
                    res = 
                    this.words
                    .replace(/a/gi, '4')
                    .replace(/b/gi, '13')
                    .replace(/e/gi, '3')
                    .replace(/g/gi, '6')
                    .replace(/i/gi, '1')
                    .replace(/o/gi, '0')
                    .replace(/s/gi, '5')
                    break;
                case 'weirdword':
                    res = 
                    Array.from(this.words)
                    .map((result, i) => {
                        if(i % 2 == 0){
                            return result.toLowerCase()
                        }else{
                            return result.toUpperCase()
                        }
                    }).join("")
                    break;
                default:
                    res = this.words.replace(/a|i|u|e|o/gi, 'i');
                    break;
            }
            return res
        }
    }
}   
</script>

<style lang="scss">
    
</style>