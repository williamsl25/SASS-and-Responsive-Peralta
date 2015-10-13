Intro to SASS

1) link sass_intro.css in head
2) serve in terminal (command d will open serve and allow you to use the terminal)
3) to compile .scss file into the sass_intro.css file on terminal type:
    node-sass style.scss sass_intro.css
4) only edit in .scss file
5) nesting (ex)
html:
  div class="box"
    <p>
      hello <span> world </span>
    </p>
    <span> It's a big world </span>
scss file:
  .box {
    width: 500px;
    height: 500px;
    background-color: red;
    p {
      margin-top: 25%;
    }
    span {
      color: white;
    }
  }
ex2)
.container {
  .cols {
    display: inline-block;
    vertical-align: top;
    &:cols-4{
      width: 24.7%
    }
  }
}
variables in SASS:
.scss file
  $quiksilverRed: #ff000;

  .container {
    background-color: $quiksilverRed;
  }

You can also create a variables.scss file to store all variables

in variables.scss
    $carolinaBlue: #7BAFDA;
    $quiksilverRed: #ff000;

in style.scss    
    @import "variables";
    @import "buttons";

    btn {
      background-color: #carolinaBlue;
    }

-mixins-
In the scss file
  @import "variables";
  @import "mixins";
  
In the mixin.scss file
EXAMPLE ONE:
DEFINE MIXIN
  @mixin val-gradient($rgba1,$rgba2,$Image){
    background:linear-gradient($rgba1,$rgba2),$Image;
    background-size: $size;
    &:hover{
      background:linear-gradient($rgba2,$rgba2),$Image;
      background-size: $size;
    }
  }
USE MIXIN
  @include val-gradient();
EXAMPLE TWO:
DEFINE MIXIN ("5%" is default value to be overriden by user input)
  @mixin border-radius($radius:5%){
    -webkit-border-radius:$radius;
    -moz-border-radius:$radius;
    border-radius:$radius;
  }
USE MIXIN
  @include border-radius();
EXAMPLE THREE
  @extend; COMMENT:This pulls in a pre-established set of styles that can then be overridden or added upon
*/
