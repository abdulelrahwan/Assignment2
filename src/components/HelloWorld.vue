<template>
  <div class="hello" style="background-color:#0064a2">
     <section>
				<div style="padding-top:20px" class="block">
        
        
              <b-checkbox v-model="displayName">
                  Name
              </b-checkbox>
  
              <b-checkbox v-model="displayRelationship">
                  Relationshop
              </b-checkbox>
					</div>
    </section>
    <b-carousel :autoplay=false style="height:600px">
        <b-carousel-item v-for="(person, i) in people" :key="i">
            <section class="hero">
                <div class="hero-body has-text-centered">
									<!-- <div class="myDIV"> -->
                    <img class="myDIV" :src="getImgUrl(person.photo)"  style="width:300px;height:300px;"/>
									<!-- </div> -->
										<div class="hide">
											<p v-if="displayName">{{person.name}}</p>
											<p v-if="displayRelationship">{{person.relationship}}</p>
										</div>
                    
                </div>
            </section>
        </b-carousel-item>
    </b-carousel>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      people: [{name: 'Beth', photo: 'grandchild1.jpg', relationship: 'Granddaughter', number: '337-444-5555'},
      {name: 'Martin', photo: 'brother.jpg', relationship: 'Brother',  number: '337-444-5555'},
      {name: 'Harry', photo: 'grandchild2.jpg', relationship: 'Grandson',  number: '337-444-5555'},
      {name: 'Joy', photo: 'neice1.jpg', relationship: 'Neice',  number: '337-444-5555'},
      {name: 'Sophia', photo: 'neice2.jpg', relationship: 'Neice',  number: '337-444-5555'},
      {name: 'Olivia', photo: 'neice3.jpg', relationship: 'Neice',  number: '337-444-5555'},
      {name: 'John', photo: 'nephew1.jpg', relationship: 'Nephew',  number: '337-444-5555'},
      {name: 'Edward', photo: 'nephew2.jpg', relationship: 'Nephew',  number: '337-444-5555'}],
      displayRelationship: true,
      displayName: true
    }
  },
  methods: {
    getImgUrl(photo) { 
      return require("../../" + photo);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.hide {
  display: none;
}

.myDIV:hover + .hide {
  display: block;
  color: red;
}
</style>
