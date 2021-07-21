# blog_website_portfolio

## 1. HTML Structure

### HEAD

- meta
    - description
    - author
    - viewport
    - keywords
- fontawesome - icons
- slideshows
    - cycle2 cdn contents delivery network: include jQuery & Cycle2 - Demo - Getting started
- Bootstrap for Grid, flex
- style.css has to come at the end for having higher priority than bootstrap

### BODY

- header
- div.banner
- div.main_content —> grid, flex
- footer

## 2. CSS

- CSS resets file
    - *better to set in one style css file for all sub-pages*
    @import url(*reset.css*); for *load the reset css file**
- fix header and align banner postion

```css
header {
	background: rgba(0,0,0,.8);
	position: fixed; /*absoulte is non-fixed with scroll*/ 
	z-index: 101; /*better power than slide images*/
}
.banner {
	position:relative;
}
```

- possible to set general height thorugh line-height
- slide show control and pager from cycle 2

```html
<head>
<!-- cycle2 cdn contents delivery network: include jQuery & Cycle2 - Demo - Getting started -->
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/1/jquery.min.js"></script>
	<script src="https://cdn.jsdelivr.net/gh/malsup/cycle2@2.1.6/build/jquery.cycle2.min.js"></script>
</head>

<body>
<div class="banner">
		<ul class="banner_list cycle-slideshow" 
		data-cycle-fx="scrollHorz" 
		data-cycle-timeout="0"
		data-cycle-slides=".slide"
		data-cycle-prev=".banner .prev"
        data-cycle-next=".banner .next"
		data-cycle-pager=".banner .custom-pager" 
		>	<!--id: #, class:.-->

			<li class="slide1 slide"> <!-- do not put the image as source, but as background for changing setting values for image-->
				<h2 class="fancy_box red main_tt">Project Title</h2> <!--class="box setting box color font*/-->
				<div class="slide_contents">
					<p>This is small description for slide. </p>
					<a href="" class="btn">See details</a> <!--giving class name, because there is also same style button in footer-->
				</div>
			</li>
```

- list style
    - float

        *1. for moving contents and adjusting the width for contents automatically*

        *2. need always to have parents for **clearfix**, if not, the heigth of parents is unclear .clearfix:after { content:''; display: block; clear:both;*

        —> flex or grid can be better than float

- hover: mouse over caption
    - :hover vs : hover

    🗨️ Be caureful with the space between : and hover

    ```css
    .project_list li .hover_contents{
    	position:absolute; left:3px; right:3px; top:3px; bottom:3px;
    	height: 100%;
    	background:rgba(0,0,0,.75); padding-top: 81px; text-align:center; 
    	**opacity:0; transition:opacity 0.4s;** 
    }

    .project_list li:hover .hover_contents {
    	opacity:1;
    }
    ```

- form input

    ```css
    .subscribe form input[type="email"] {
    	width: 300px; height: 56px; display: inline-block;
    	padding: 0 20px; border: none;
    	font-style: italic;
    	color: #000;
    }
    .subscribe form input[type="email"]::placeholder { /*give different color for placeholder & type text */
    	color: #989898;
    }
    .subscribe form input[type="submit"] {
    	vertical-align: bottom; /*뒤에 따라오는 item의 높낮이가 앞의 것과 맞춰짐*/
    }
    ```

## 3. Subpages

- make clear what is the same apperances and different apperances —> class name

## 4. From px version to Bootstrap Flex

- need to have a parent for grid or flex

```html
<!--bootstrap-->
	<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
</head>
<body>
<div class="container clearfix">
	<!--navbar: need to have a parent for grid-->
			<div class="row main_nav"> 
				<h1 class="logo col-md-auto">
					<a href="index.html">MinasPortfolio</a> 
				</h1>
				<nav class="col-md-auto">
					<ul class="clearfix">
						<li><a href="index.html">Home</a></li> <!--logo image replacement with text for better searching than just image without text-->
						<li><a href="portfolio.html">Portfolio</a></li>
						<li><a href="about.html">About us</a></li>
					</ul>
				</nav>
			</div>
		</div>

<!--main_content-->
	<div class="main_content container">
		<h3 class="content_tt">Recent Projects</h3>
		<p class=link><a href="#">See all projects &rarr;</a></p>
		<ui class="project_list row">
			<li class="col-md-4 col-sm-12 col-12">
				<div class="inner_border">
					<img src="images/portfolio-thumb-1.jpg" alt="portfolio-thumb"/>
					<div class="hover_contents">
							<h4 class="content_tt">This is the project name.</h4>
							<a href="#">click for details</a>
					</div>
				</div>
			</li>
```
