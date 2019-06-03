<script type="text/javascript" src="{{ base.url | prepend: site.url }}/assets/miniMathJax/MathJax.js?config=TeX-AMS_SVG"></script>
<script type="text/javascript" src="{{ base.url | prepend: site.url }}/assets/js/jsxgraphcore.js"></script>

<style type="text/css">
	div.jsxbox {
		/*border: 1px solid black;*/
		width: 100%;
		max-width: 500px;
		margin: auto;
	}
	div.jsxbox:before{
		content: "";
		float: left;
		padding-bottom: 100%;
	}
	div.jsxbox:after{
		content: "";
		display: table;
		clear: both;
	}
	.flexContainer {
		max-width: 800px;
		margin: 0 auto;
		display: flex;
		justify-content: center;
	}
	.column {
		height: 300px;
		width: 300px;
		/*border: 1px solid black;*/
	}
</style>

## The Inverse Function Theorem

### Revision of Injectivity

Recall that a function is injective if it doesn't map two distinct points to the same point.

<div class="flexContainer">
<div class="column" id="box5"></div>
<div class="column" id="box6"></div>
</div>
<script type="text/javascript">
function createBox5() {
	JXG.Options.text.useMathJax = true;
	var brd = JXG.JSXGraph.initBoard('box5',
		{
			// xmin, ymax, xmax, ymin
			boundingbox: [-0,10,10,-0],
			axis:false,
			showCopyright:false,
			showNavigation:false
		}
	);

	var label =brd.create('text',[4,9,"Injective"],{fontSize:18});

	var one = brd.create('point',[3,7],{fixed:true,withLabel:false});
	var two = brd.create('point',[3,5],{fixed:true,withLabel:false});

	var A = brd.create('point',[7,7],{fixed:true,withLabel:false});
	var B = brd.create('point',[7,5],{fixed:true,withLabel:false});
	var C = brd.create('point',[7,3],{fixed:true,withLabel:false});

	var setX = brd.create('text',[3,1,"X"],{fontSize:18});
	var setY = brd.create('text',[7,1,"Y"],{fontSize:18});
	var g = brd.create('text',[5,1.5,"f"],{fontSize:18,color:"#0000bb"});
	var func = brd.create('arrow',[[setX.X()+0.6,setX.Y()],[setY.X()-0.1,setY.Y()]]);

	var fone = brd.create('arrow',[one,[A.X()-0.1,A.Y()]]);
	var ftwo = brd.create('arrow',[two,[B.X()-0.1,B.Y()]]);
}
createBox5();
</script>
<script type="text/javascript">
function createBox6() {
	JXG.Options.text.useMathJax = true;
	var brd = JXG.JSXGraph.initBoard('box6',
		{
			// xmin, ymax, xmax, ymin
			boundingbox: [-0,10,10,-0],
			axis:false,
			showCopyright:false,
			showNavigation:false
		}
	);

	var label =brd.create('text',[3.5,9,"Not Injective"],{fontSize:18});

	var one = brd.create('point',[3,7],{fixed:true,withLabel:false});
	var two = brd.create('point',[3,5],{fixed:true,withLabel:false});

	var A = brd.create('point',[7,7],{fixed:true,withLabel:false});
	var B = brd.create('point',[7,5],{fixed:true,withLabel:false});
	var C = brd.create('point',[7,3],{fixed:true,withLabel:false});

	var setX = brd.create('text',[3,1,"X"],{fontSize:18});
	var setY = brd.create('text',[7,1,"Y"],{fontSize:18});
	var g = brd.create('text',[5,1.5,"g"],{fontSize:18,color:"#00bb00"});
	var func = brd.create('arrow',[[setX.X()+0.6,setX.Y()],[setY.X()-0.1,setY.Y()]],{strokeColor:"#00bb00"});

	var fone = brd.create('arrow',[one,[A.X()-0.1,A.Y()]],{strokeColor:"#00bb00"});
	var ftwo = brd.create('arrow',[two,[A.X()-0.1,A.Y()]],{strokeColor:"#00bb00"});
}
createBox6();
</script>

We express this formally using the following definition:

*Definition:*
If $$X$$ and $$Y$$ are sets and $$f:X \rightarrow Y$$ is a function then $$f$$ is <em>injective</em> iff for any two points $$x,x'\in X$$ such that $$x\neq x'$$ then $$f(x)\neq f(x')$$.

Recall that if $$X$$ and $$Y$$ are sets and $$f:X \rightarrow Y$$ is a function between them then $$f$$ is *injective* iff for any two points $$x,x'\in X$$ such that $$f(x)=f(x')$$ we have in fact that $$x=x'$$.
In the case of functions $$f:\mathbb{R} \rightarrow \mathbb{R}$$ a function is injective iff it is strictly increasing or decreasing.
For instance in the following diagram

<div class="flexContainer">
<div class="column" id="box3"></div>
</div>
<script type="text/javascript">
function createBox3() {
	JXG.Options.text.useMathJax = true;
	var brd = JXG.JSXGraph.initBoard('box3',
		{
			// xmin, ymax, xmax, ymin
			boundingbox: [-3,5,3,-1],
			axis:true,
			showCopyright:false,
			showNavigation:false
		}
	);
	function f(x){return x+1;}
	function g(x){return 3;}
	var func = brd.create('functiongraph',[f],{name:'f(x)=x+1'});
	var funcg = brd.create('functiongraph',[g],{strokeColor:"#00bb00"});
}
createBox3();
</script>
the blue line $$f(x)=x+1$$ is injective but the flat green line $$g(x)=3$$ is not.
To see that $$g$$ is not injective we only need to show that there are two distinct points sent to the same point.
For instance we observe that $$g(1)=3=g(-2)$$ but clearly $$1\neq -2$$.
The following diagram shows the graph of $$f(x)=\frac{1}{10}x^3+3$$ in blue and the graph of $$g(x)=-x^2+2$$ in green:
<div class="jsxbox" id="box4"></div>
<script type="text/javascript">
function createBox4() {
	JXG.Options.text.useMathJax = true;
	var brd = JXG.JSXGraph.initBoard('box4',
		{
			// xmin, ymax, xmax, ymin
			boundingbox: [-3,5,3,-1],
			axis:false,
			showCopyright:false,
			showNavigation:false
		}
	);
	function f(x){return -x*x+2;}
	function g(x){return 0.1*x*x*x+3;}
	var func = brd.create('functiongraph',[g]);
	var funcg = brd.create('functiongraph',[f],{strokeColor:"#00bb00"});
}
createBox4();
</script>


### The Definition of Derivative

If $$f:\mathbb{R}^n \rightarrow \mathbb{R}^m$$ is a function and $$\vec{x}_0\in \mathbb{R}^n$$ then <em>a linear map $$\alpha$$ is a derivative for $$f$$ at $$\vec{x}_0$$</em> iff there exists a neighbourhood $$U$$ of $$\vec{x}_0$$ and a function $$\epsilon:U \rightarrow \mathbb{R}^m$$ and such that for all $$\vec{x}\in U$$:

$$f(\vec{x}) = f(\vec{x}_0) + \alpha(\vec{x}-\vec{x}_0) + \epsilon(\vec{x})\|\vec{x}-\vec{x}_0\|$$

and $$\epsilon(\vec{x}) \to 0$$ as $$\vec{x} \to 0$$.

### The One Dimensional Inverse Function Theorem

Let $$f:\mathbb{R}\rightarrow \mathbb{R}$$ and $$\alpha\in \mathbb{R}$$ be the derivative of $$f$$ at $$-1$$.
Then the following equation holds

$$f({x}) = f({x}_0) + \alpha\cdot({x}-{x}_0) + \epsilon({x})|{x}-{x}_0|$$

where $$\epsilon$$ is a function of $$x$$ such that $$\epsilon(x)\to 0$$ as $$x\to 0$$.
In the diagram below the blue curve is the function $$f(x)$$ and we further assume that the derivative of $$f$$ at $$x=-1$$ is not zero.
The black line is the linear approximation to $$f(x)$$ at $$x$$.
The red line shows the size of the error term $$\epsilon(a)$$.
Move the red point to see how the error changes with $$a$$.

<div class="jsxbox" id="box"></div>
<script type="text/javascript">
function createBox1() {
	JXG.Options.text.useMathJax = true;
	var brd = JXG.JSXGraph.initBoard('box',
		{
			// xmin, ymax, xmax, ymin
			boundingbox: [-1.7,2,0,-0.5],
			axis:true,
			showCopyright:false,
			showNavigation:false
		}
	);
	function f(x){return x*(x-1)*(x+1)+1;}
	function deriv(x){return 3*x*x-1;}
	var x0 = -1;
	var base = brd.create('point',[x0,f(x0)],{color:"#0000ff",name:"$$(x,f(x))$$",label:{fontSize:18,offset:[0,-20],strokeColor:"#0000ff"}});
	function approx(x){return f(x0)+(x-x0)*deriv(x0);}
	var func = brd.create('functiongraph',[f]);
	var funcApprox = brd.create('functiongraph',[approx],{withLabel:true, strokeColor:"#000000", fixed:true, name:"$$f(x)+\\alpha(x-a)$$",label:{fontSize:18,offset:[150,230]}});
	var u0 = -1.25;
	var u1 = -0.75;
	var U = brd.create('segment',[[u0,0],[u1,0]],{strokeColor:"#00ff00",fixed:true});
	var point = brd.create('point',[u0,0],{name:"$$a$$",label:{fontSize:18, strokeColor:"#ff0000",offset:[10,15]}});
	brd.on('move',function(){
		if (point.Y() != 0) {
			point.moveTo([point.X(),0]);
		}
		if (point.X() < u0) { point.moveTo([u0,0]); }
		if (point.X() > u1) { point.moveTo([u1,0]); }
	});
	var error = brd.create(
		'segment',
		[function(){return [point.X(),f(point.X())];},function(){return [point.X(),approx(point.X())];}],
		{
			strokeColor:"#ff0000",
			name:"$$\\|x-a\\|\\epsilon(a)$$",
			withLabel:true,
			label:{
				strokeColor:"#ff0000",
				fontSize:18,
				offset:[-100,25]
			}
		}
		);
}
createBox1();
</script>

Notice that we have chosen the green interval small enough so that the red error is never large enough to 	make the blue curve 'bend back on itself'.
More precisely we have chosen the green interval small enough so that the function $$f$$ is injective on the green interval.

But can we always do this?
In general we cannot.
For instance consider the function $$f(x)=x^2$$ at the point $$x=0$$:

<div class="jsxbox" id="box2"></div>
<script type="text/javascript">
function createBox2() {
	JXG.Options.text.useMathJax = true;
	var brd = JXG.JSXGraph.initBoard('box2',
		{
			// xmin, ymax, xmax, ymin
			boundingbox: [-3,5,3,-1],
			axis:true,
			showCopyright:false,
			showNavigation:false
		}
	);
	function f(x){return -x*x+3;}
	function deriv(x){return 2*x;}
	var x0 = 0;
	var base = brd.create('point',[x0,f(x0)],{color:"#0000ff",name:"$$(x,f(x))$$",label:{fontSize:18,offset:[0,-20],strokeColor:"#0000ff"}});
	function approx(x){return f(x0)+(x-x0)*deriv(x0);}
	var func = brd.create('functiongraph',[f]);
	var funcApprox = brd.create('functiongraph',[approx],{withLabel:true, strokeColor:"#000000", fixed:true, name:"$$f(x)+\\alpha(x-a)$$",label:{fontSize:18,offset:[150,230]}});
	var u0 = -1.25;
	var u1 = 1;
	var U = brd.create('segment',[[u0,0],[u1,0]],{strokeColor:"#00ff00",fixed:true});
	var point = brd.create('point',[u0,0],{name:"$$a$$",label:{fontSize:18, strokeColor:"#ff0000",offset:[10,15]}});
	brd.on('move',function(){
		if (point.Y() != 0) {
			point.moveTo([point.X(),0]);
		}
		if (point.X() < u0) { point.moveTo([u0,0]); }
		if (point.X() > u1) { point.moveTo([u1,0]); }
	});
	var error = brd.create(
		'segment',
		[function(){return [point.X(),f(point.X())];},function(){return [point.X(),approx(point.X())];}],
		{
			strokeColor:"#ff0000",
			name:"$$\\|x-a\\|\\epsilon(a)$$",
			withLabel:true,
			label:{
				strokeColor:"#ff0000",
				fontSize:18,
				offset:[-100,25]
			}
		}
		);
}
createBox2();
</script>

The inverse function theorem tells us that if $$f$$ is a differentiable function and $$x$$ is a point in the domain of $$f$$ such that the derivative of $$f$$ at $$x$$ is invertible then we can always find an open set around $$x$$ on which $$f$$ is injective.
