< !-- general notes from 6/8 -->use debug- recommended,
I never used it yesterday I wonder how that could have helped. 

container-row-column 

create variables in css:root {
  --colorname: #f8f7f2;
}

//main
container row~hero-image~custom class .hero-image -- used to add a background image to the whole row using .hero-image {
  background-image: url(xxx) height: 50vh background-size: cover;
  background-positon: x% x%; //is findable within developer tools
  background-repeat: no-repeat;
}

custom class~glass-box~.glass-box {
  copied from and altered slightly from https: //css.glass/
}

using at media to make changes to the css with things like screen size. ex // medium is 768px

@media (max-width: 768px) {

  // these rules will apply when below this size
  .specific-class {
    //previously set class
    border-left: none;
    border-right: none;
    border-top: 3px solid black;
    border-bottom: 3px solid black;
  }
}

position-(absolute/relative) you can nest absolutes within relative elements to designate the position of elements regardless of viewport in relation to the partent element.
 div~position-relative p~position-absolute (top: 50% right 50%)
/* Setting up formatter alt+shift+f */