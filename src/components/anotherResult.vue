<template>
  <div class="">
    <!--<p>Counter is: {{ counter }}</p> -->
    <p>Counter is: {{ dblcounter }}</p>
    <p>Number of click is: {{ stringCounter }}</p>
  </div>

</template>

<script>
/*export default {
  computed: {
    counter () {
      // return this.$store.state.counter * 2
      return this.$store.getters.dblcounter
    }
  }
}
*/
// using mapGetters
import {
  mapGetters
} from 'vuex'

/*export default {
  computed: mapGetters([
    'dblcounter',
    'stringCounter'
  ])
}
*/
export default {
  computed: {
    ...mapGetters([
      'dblcounter',
      'stringCounter'
    ])
  }
}
</script>

<!-- so here vuex need to be improvize if we have tons of files then everytime we have to paste the code there

so for that we have another solution
for that instead of directly access from centerlized data we can create a getter which get the state from the store and perform required action or caluculation and then getter we will used in all diffrent components
So getters is reserved keywork you have to use it.
 -->

 <!-- So what if we have more getters
 so vuex provide a features where we can access convineantly all getters without setting manually computed property
 so vuex has helper function called mapGetters wo for that we need to import first to use it.
  -->

  <!-- Now if we access or want to create your own custom  for that we need create and object and put mapGetters inside of it that will not work because we have object and imediatly have another object that is not valid code so for that we need to spread operator with es6
this ... (3 dots) basically allow us to pull out all the methods and properties we have in the object so mapGetters is an object and have properties in it so pullout them all out of there and creates saprate key value pairs for each of them.
so now we can write our own custom computed properties.
like:-
export default {
  computed: {
    ...mapGetters([
      'dblcounter',
      'stringCounter'
    ]),
    ourOwn(){

    }
  }
}

behind the scene spred operator does like this
export default {
  computed: {
    mapGetters (){
      dblcounter: dblcounter
      stringCounter: stringCounter
    },
    ourOwn(){
      console.log('custom property')
    }
  }
}
-->

<!-- After all this still we get error in console like Unexpected token because of spread operator
so the in package.json we are using bable that convert es6 to es5 but that is not conver rest and spread operator yet so for that we need install to get functionalty to work
npm install -save-dev babel-preset-stage-2

after installed this now go to the file .babelrc file and add new entry
["stage-2"]
and restart development server again to get work.
 -->
