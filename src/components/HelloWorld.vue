<template>

  <div class="container-fluid">
  <article class="main-image">
    <section>
      
      <h1>Brent Shierk</h1>
      <span>Full stack developer</span>
      <button class="btn btn-xl btn-light" @click="scrollTo('find-more')">About me</button>
    </section>
  </article>    
   
   <article id="find-more" class="white-section">
     <section>
       <h3>
        About Me
       </h3>
       <span>Since beginning my journey as a Software developer 2 years ago, I've done remote work for agencies, created digital products for both business and consumer use. I'm quietly confident, naturally curious, and perpetually working on improving my abilities one problem at a time
</span>
       <button class="btn btn-xl btn-dark" @click="scrollTo('offers')">My Skill</button>
     </section>
   </article>

   <article id="offers" class="blue-section">
     <section class="container">
       <h2>Skills</h2>
      <div class="row">
        <div class="col-lg-3 col-md-6 mb-5 mb-lg-0" v-for="(offer, index) in offers" :key="index">
          <div class="icon mx-auto"><i class="fas" :class="offer.icon">
            <b-icon :icon="offer.icon"></b-icon>
            </i></div>
          <h4>{{offer.title}}</h4>
          <span>{{offer.description}}</span>
        </div>

      </div>
             <button class="btn btn-xl btn-dark" @click="scrollTo('recent-projects')">portfolio</button>

     </section>
   </article>

   <article class="second-image"> 
     <section>
       <h2 class="port-head">portfolio</h2>
       <!-- <button class="btn btn-xl btn-dark" @click="scrollTo('recent-projects')">recent projects</button> -->
     </section>
   </article>

   <article id="recent-projects" class="portfolio-section">
     <section class="container">
       <h3>recent projects</h3>
       <div class="row no-gutters">
       <div class="col-lg-6" v-for="(project, index) in recentProjects" :key="index">
         <h5>{{project.title}}</h5>
         <!-- <p>{{project.description}}</p> -->
         <a :href="project.link" class="portfolio-item">
           <span class="caption">
             <span class="caption-content">
               <!-- <h2 class="project-title">{{project.title}}</h2> -->
               <!-- <p class="mb-0 project-dist">{{project.description}}</p> -->
               
               
             </span>
           </span>
           
           <img class="img-fluid" :src="require('../assets/'+project.img)" alt="" :href="project.link">
          
         </a>
         </div>
       </div>
     </section>
   </article>

   

     
   <footer>
     <h1>contact me</h1>
     <img src="../assets/github.png" alt="" >
     <img src="../assets/linkedin.png" alt="">
   </footer>
  </div>
  
</template>

<script>

export default {
  name: "HelloWorld",
  
  props: {
    msg: String
  },
  data(){
    return{
      offers: [
        {
          icon: 'phone',
          title: 'Responsive design',
          description: 'Expierence building reactive web applications using component based libaries like Vue and React'
        },
        {
          icon: 'cloud-upload',
          title: 'Cloud usage',
          description: 'Using cloud based software for for api endpoint conectivity '
        },
        {
          icon: 'terminal',
          title: 'Development',
          description: 'fullstack web development expierence using Javascrippt, Ruby on rails and Python '
        },
        {
          icon: 'archive',
          title: 'Database managment',
          description: 'working with and creating sql and nosql databases'
        }
      ],
      recentProjects:[
        {
          img: 'igm1.png',
          title:'Keisha Villerson fitness App',
          description:'built a fullstack web app',
          link: 'https://github.com/bshierk1996/pt2'
        },
        {
          img: 'dogs.png',
          title:'Foster Dogs',
          description:'Ruby on rails App',
          link: 'https://github.com/bshierk1996/foster_dogs_development'
        },
        {
          img: 'NYT.png',
          title:'NYT webscraper',
          description:'NYT web scraper',
          link:'https://github.com/bshierk1996/homework-newyorktimes/tree/master/newyorktimes'
        },
        {
          img: 'friend.png',
          title:'friend finder app',
          link:'https://github.com/bshierk1996/friend/tree/master/friendFinder-master',
          description:'friend finder'
        },
      ],
      socialMedia:[
        {
          link:'../assets/linkedin.png'
        },
        {
          link:'../assets/github.png'
        }
      ]
    }
  },
  methods:{
    scrollTo(element){
      const el = document.querySelector('#'+element);
      el.scrollIntoView({
        behavior: 'smooth',
        block: 'start'
      })
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped >
h5{
  margin-top: 
    10px;
  
}
article{
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  padding: 0 10px;
}
.btn-xl{
  padding: 20px 35px;
  font-size: 1.25rem
}
.main-image{
  min-height: 100vh;
  background-size:cover;
  padding: 0 10px;
  text-align: center;
  background-position-y: -380px;

}
.main-image{
background:url('../assets/background-img.jpg') center center;
  background-position-y: -380px;

}
span{
  display: block;
  padding-bottom: 30px;
  font-size: 1.6rem;
  
}
h3{
  color: black;
  font-size: 2rem;
  font-weight: bold;
}
.white-section{
  padding: 100px 10px;
  background-color: #fff;
  text-align: center
}
.port-head{
  margin-top: 60px;
}
.portfolio-section{
  padding: 0px 10px;
  background-color: #fff;
  text-align: center;
  margin-top: 20px;
}

.blue-section{
  padding: 120px 10px;
  background-color: #1d809f;
  color: #fff;
  text-align: center;

}
h2{
  font-size: 3rem;
  font-weight: bold;
  margin-bottom: 50px;
}
h4{
  font-size: 1.6rem;
  padding-top: 20px;
}
.icon{
  display: flex;
  justify-content: center;
  align-items: center;
  width: 120px;
  height: 120px;
  background: #fff;
  color: #1d809f;
  border-radius: 50%;
}
i{
  font-size: 2rem;

}
.row{
  padding-top: 50px;
}
.portfolio-item{
  display: block;
  position: relative;
  overflow: hidden;
  transition: transform .2s linear;
  &:hover{
    transform: scale(.9)
  }  
}
.caption{
  display: flex;
  height: 100%;
  width: 100%;
  position: absolute;
  top: 0;
  bottom: 0;
  z-index: 1;
  // background-color: rgba($color: #000000, $alpha: .2); 
  transition: transform .2s linear;
  
}
.caption-content{
  text-align: left;
  color: #fff;
  margin: auto 2rem 2rem;
}


.caption{
  transform: scale(.9);
  /* background-color: rgba($color: #000000, $alpha: .2); */
}
.project-title{
color: black
}
.project-dist{
color: black
}
.social{
  size: 40px;
}
.icon{
  height: 100px;
  width:100px;
  margin: 0;
}
footer{
  padding: 10px 10px;
  background-color: #1d809f;
  color: black
}
</style>
