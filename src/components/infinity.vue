<template>
  <div>
<div class="container">
  <div class="row">
    <div class="col-sm">
      <h1>HERO</h1>
      <p>
        <img v-bind:style="{width: aHero.hp*2 + 'px'}" :src="HP1" alt height="50px">
      </p>
       <p style="font-size: 200%">HP :{{aHero.hp}}</p>
      <p>
        <img style="width:400px" :src="aHero.image"/>
      </p>
      <p style="font-size: 200%">{{aHero.name}}</p>
    </div>
    <div class="col-sm">
     <button v-bind:disabled="finisd" @click="start()"> Start</button>
     <button v-bind:disabled="finisd" @click="attack()"> Attack</button>
     <button v-bind:disabled="finisd" @click="specialattack()"> Special Attack</button>
     <button @click="restart()"> Restart</button>
     <br>
     <br>  
     <br> <img src="https://imgur.com/J4eR5Rs.png" width="100%">
     <br>
     <br>
     <br>  
     <div id="end">
     <div v-if="aHunter.hp <=0">HERO  IS  WINNER</div>
     <div v-else-if="aHero.hp <=0">HUNTER  IS  WINNER</div>
    </div>
    </div>
    <div class="col-sm">
     <h1>HUNTER</h1>
     <p>
        <img v-bind:style="{width: aHunter.hp*2 + 'px'}" :src="HP2" alt height="50px">
      </p>
      <p style="font-size: 200%">HP :{{aHunter.hp}}</p>
       <p>
        <img style="width:400px" :src="aHunter.image"/>
      </p>
      <p style="font-size: 200%">{{aHunter.name}}</p>
    </div>
  </div>
</div>
    
    
  </div>
</template>

<script>
export default {
  data:function() {
    return {
     
     player:[
        {name:'Poomy',hp:50,image:"https://imgur.com/h9RhkPL.png" },
        {name:'nighty',hp:90,image:"https://imgur.com/bHxCvmp.png" },
        {name:'somzy',hp:120,image:"https://imgur.com/LlHLabG.png" },
        {name:'stangky',hp:150,image:"https://imgur.com/7Ukwzsa.png" },
       {name:'commy',hp:170,image:"https://imgur.com/oVBDpY0.png" },
       {name:'herry',hp:200,image:"https://imgur.com/zvGZB59.png" },
      
      ],
    Hunter:[
        {name:'Batty',hp:50 ,image:"https://imgur.com/Oiqh8CQ.png" },
        {name:'booky',hp:90,image:"https://imgur.com/DqP4Bnj.png" },
        {name:'dongky',hp:120,image:"https://imgur.com/DpksZG8.png" },
        {name:'prterry',hp:150,image:"https://imgur.com/aMggJno.png" },
        {name:'yennzy',hp:170,image:"https://imgur.com/4gAWNeZ.png" },
        {name:'Sunkung',hp:200,image:"https://i.imgur.com/714BGqG.png" },
        ],
         
       aHero:{name:"",HP:0,image:""},
       aHunter:{name:"",HP:0,image:""},
      A:"",
      D:"",
      HP1:"https://i.ppy.sh/bca61e3c2183a86ddb4c1d75914fab845e2b128f/687474703a2f2f692e696d6775722e636f6d2f6953766c5662432e706e67?fbclid=IwAR3HXqqNPWD_6W3OHaA9vpYY7LInoHK9GNylOSg7XHVQTzPbQYsyMINnYmY",
      HP2:"https://i.ppy.sh/bca61e3c2183a86ddb4c1d75914fab845e2b128f/687474703a2f2f692e696d6775722e636f6d2f6953766c5662432e706e67?fbclid=IwAR3HXqqNPWD_6W3OHaA9vpYY7LInoHK9GNylOSg7XHVQTzPbQYsyMINnYmY",
      finisd: false,   
    }




  },

    methods: {randomno: function (min,max) {
      return Math.max(Math.floor(Math.random()*max)+1,min);
    },
     start : function (){
       this.aHero= this.player[this.randomno(0,6)-1];
       this.aHunter= this.Hunter[this.randomno(0,6)-1];
     },
     attack : function(){
       this.A=this.randomno(2,10);
       this.aHero.hp =this.aHero.hp-this.A;
       this.D=this.randomno(2,10);
       this.aHunter.hp =this.aHunter.hp-this.D;
       if (this.aHero.hp <=0){
         this.aHero.hp =0;
         this.finisd =true;
      }else if (this.aHunter.hp <=0){
         this.aHunter.hp =0;
          this.finisd =true;
      }
     
     },
      specialattack : function(){
       this.A=this.randomno(10,15);
       this.aHero.hp =this.aHero.hp-this.A;
       this.D=this.randomno(10,15);
       this.aHunter.hp =this.aHunter.hp-this.D;
       if (this.aHero.hp <=0){
         this.aHero.hp =0;
         this.finisd =true;
      }else if (this.aHunter.hp <=0){
         this.aHunter.hp =0;
          this.finisd =true;
      }
     
     },
    restart: function () {
      window.location.reload();
    },
  },
}

</script>

<style>
#end {
  font-size: 200%;
  color: darkred;
}
</style>