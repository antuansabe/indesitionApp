<template> 
    <h2> {{ customTitle }} </h2>
    <p> {{ counter }}   <sup> 2 </sup>  = {{ squareValue  }}  </p>


<div>
    <button v-on:click="increase"> +1</button>
    <button v-on:click="decrease"> -1 </button>
</div>

</template>

<script>
import { numberLiteralTypeAnnotation } from "@babel/types";

export default {
    props: {
        title: String,
        start: {
            type: Number,
            default: 100,
            require: true,
            valdator( value ) {
                return value > 100
            }
        }
    },

    data() {
        return {
            counter: this.start
        }
    },
    methods: {
        squareCounter() {
            console.log('getSquareValue')
            return this.counter * this.counter;
        },
        increase() {
            this.counter++
        },
        decrease() {
            this.counter--
        }
        },
        computed: {
        squareValue() {
            return this.counter * this.counter
        },
        customTitle() {
            return this.title ? this.title : 'Counter'
        }
    }

}
</script>

<style>
    button{
        background-color: #64BB87 ;
        border-radius: 5px;
        color:white;
        margin: 0 5px;
        cursor: pointer;
        padding: 5px 15px;
        transition: 0.3s ease-in-out;
    }

    button:hover {
        background-color: rgb(32, 102, 164);
        transition: 0.3s ease-in-out;
    }


</style>
