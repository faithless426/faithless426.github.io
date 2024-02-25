    ---
    layout: page
    title: Classical Mechanics #1
    description: Newtons Equations, Galilean Spacetime, Calculus of Variations
    category: classical mechanics 
    img: E5GDY.png
    ---

This is the first section of notes for Classical Mechanics!

The goal for this series is to thoroughly cover classical mechanics at a level that can be appreciated by physics and math people at an undergraduate to graduate level. I'll hopefully be able to indicate different section of math vs physics but we'll see how it goes. 

I'll be taking my notes from the classes that I've taken, my personal adds, and the following books: 

1. Classical Mechanics by Herbert Goldstein, Charles Poole, John Safko

2. Classical Dynamics: A Contemporary Approach by Jorge V. José, Eugene J. Saletan

3. Mathematical Methods of Classical Mechanics by V.I. Arnold

4. Introduction to Mechanics and Symmetry by Jerold E. Marsden, Tudor S. Ratiu

5. Mechanics by L.D. Landau, E.M. Lifshitz

6. Mathematical Aspects of Classical and Celestial Mechanics by Vladmir I. Arnold, Valery V. Kozlov, Anatoly. I Neishtadt 

7. The Variational Principles of Mechanics by Cornelius Lanczos

8. Introduction to Dynamics by I.C. Percival, D. Richards

9. Foundations of Mechanics by Ralph Abraham, Jerrold E. Marsden

10. Geometric Mechanics by Waldyr Muniz Oliva 

11. Classical Mechanics with Calculus of Variants and Optimal Control: An Intuitive Introduction

12. Modern Classical Mechanics by T.M. Helliwell, V.V. Sahakian

13. Symplectic Geometry and Integrable System Lecture Notes by Anton Izosimov

14. Lectures on Symplectic Geometry by Ana Cannas da Silva

15. Introduction to Symplectic Topology by Dusa McDuff, Dietmar Salamon

16. Symplectic Invariants and Hamiltonian Dynamics by Helmut Hofer, Eduard Zehnder

17. Symplectic Geometry and Analytic Mechanics by Paulette Libermann and Charles-Michel Marle

18. Calculus of Variations by I.M. Gelfand, S.V Fomin

19. Variational Calculus by Jean-Pierre Bourguignon

20. Calculus of Variations: With Applications to Physics and Engineering by Robert Weinstock

21. A First Course in the Calculus of Variations by Mark Knot

22. Lectures on the Calculus of Variations and Optimal Control Theory by L.C. Young

23. Symplectic Topology and Floer Homology: Volume 1 by Yong-Geun Oh

Among other resources for background information which I will unfortunately have to assume you know basic Newtonian physics(with calculus), linear algebra, some ODE, and some differential geometry. However, I will offer a review of the topics as needed. 

While this is a laundry list of book that I admittedly havent read through completely. These will be ever changing lecture notes that will be continually updated and more books will definitely be added. 

Being that this is the introduction section let's quickly go over Newtonian mechanics as well as some new math, the calculus of variations. 

Newton's formulation of Mechanics begins with his namesake equation 

$$\begin{aligned} \vec{F} &=m\vec{a}\\ &=m\frac{d\vec{v}}{dt}\\ &=m\frac{d^2\vec{r}}{dt^2} \end{aligned}$$

Where $\vec{a}$ is the acceleration, $\vec{v}$ is the velocity, and $\vec{r}$ is the position. (I may at times forget the vector notation). We will assume that we live in $\mathbb{R}^3$ with time $t\in\mathbb{R}$ being a parameter (i.e living in $\mathbb{R}\times \mathbb{R}^3$, and for those more mathematically inclined I will later explain this is an affine space $A^4$). 

We see that Newton's equations gives us $3N$ for $N$ particles, but for the most part we'll focus on the single particle case. As an example let's do the simple case of a constant force, gravity.

The force of gravity is given by the following equation 

$$\vec{F}=-m\vec{g}$$

with $g=9.81$ being the graviational constant which acts in the $z$ direction. Our differential equation then becomes 

$$\begin{aligned}m\vec{a}&=-m\vec{g}\\\begin{pmatrix}\frac{d^2x}{dt^2}\\\frac{d^2y}{dt^2}\\\frac{d^2z}{dt^2}\end{pmatrix}&=\begin{pmatrix}0\\0\\-g\end{pmatrix}\end{aligned}$$

Solving these second order differential equations we get the solution

$$\begin{pmatrix}x(t)\\y(t)\\z(t)\end{pmatrix}=\begin{pmatrix}c^{x}_{1}t+c^{x}_{2}\\c^{y}_{1}t+c^{y}_{2}\\-gt^2+c^{z}_{1}t+c^{z}_{2}\end{pmatrix}$$

With $c_x,c_y,c_z$ being constants determined by initial conditions(i.e the initial velocities and positions).

Cool, awesome even. We won't get into force diagrams and the like but now we know how idealized objects evolve (hint hint dynamical systems hint hint). As long as we know some initial conditions and assume (or get from an experiment) some reasonable force we can calculate the exact path that this object will take. However, the current form of Newton's equations aren't the most convenient. Solving Newton's equations in it's most basic form is solving a second order ODE for a force in time, but often physicists are more conserned with forces that are position dependent such as gravity (unfortunate that I did solve this before normally but still). Fortunately we can do this in systematic way.

Let's first introduce a quantitity known as momentum. 

$$\vec{p}=m\vec{v}$$

This quantity ends up being more fundamental due to it being velocity dependent, and let's us rewrite Newton's equations as such 

$$\vec{F}=\frac{d\vec{p}}{dt}=m\frac{d\vec{v}}{dt}$$

Alright back to solving. So the form of Newton's equation we want to solve is the following

$$m\frac{d\vec{v}}{dt}=F(\vec{r})$$

As normal let's integrate to solve this ODE (we'll generalize the calculation to arbitrary dimension later) 

$$m\int_{x_i}^{x_f} \frac{dv}{dt}dx=\int_{x_i}^{x_f} F(x)dx$$

We do a simple subsitution for the LHS of the equation

$$\begin{aligned} u &=x\\ \frac{du}{dt} &=\frac{dx}{dt} \\ du&=vdt\end{aligned}$$

Our integral then becomes (

$$\begin{aligned}m\int_{x_i}^{x_f} \frac{dv}{dt}dx&=m\int_{t_i}^{t_f} \frac{dv}{dt}vdt\\&=m\int_{t_i}^{t_f}vdv\\&=\frac{1}{2}mv^{2}_{f}-\frac{1}{2}mv^{2}_{i}=\int_{x_i}^{x_f} F(x)dx\end{aligned}$$

We're very free to make this a function of $x$ by making the previous integral an indefnite one by the changing the bounds. 

We'll call the quantity $\frac{1}{2}mv^2$ the kinetic energy ($K$) and refer to the result we derived as the Work-Energy Theorem. I recommend you use this to solve the equation for the harmonic oscillator ($F=-kx$) for practice. 

Now to do this in the multi-dimensional case. Imagine we have a path $\gamma$ such that $\gamma:[a,b]\rightarrow \mathbb{R}^3$, and have a force $\vec{F}$ that successfuly takes our mass from point $a$ to $b$. This curve has some infinitesimal length that we'll call $d\vec{r}$ and the force acts on this every point on this path which is represented as a dot product $\vec{F}\cdot d\vec{r}$. We'll go through a similar procress as above, i.e. 

$$\vec{F}\cdot d\vec{r}=m\frac{d\vec{v}}{dt}\cdot d\vec{r}$$

We simply integrate:
$$\int_{\vec{r_i}}^{\vec{r_f}}F(\vec{r})\cdot d\vec{r}=m\int_{\vec{r_i}}^{\vec{r_f}}\frac{d\vec{v}}{dt}\cdot d\vec{r}$$

Then we do a similar change of variables to rewrite the RHS

$$m\int_{\vec{r_i}}^{\vec{r_f}}\frac{d\vec{v}}{dt}\cdot d\vec{r}=m\int_{t_i}^{t_f}\frac{d\vec{v}}{dt}\cdot \vec{v}dt$$

We can solve this integral by taking note of a convenient vector identity

$$\frac{d}{dt}(\vec{v}\cdot\vec{v})=\frac{d\vec{v}}{dt}\cdot\vec{v}+\vec{v}\cdot\frac{d\vec{v}}{dt}=2\left(\frac{d\vec{v}}{dt}\cdot\vec{v}\right)$$
$$\implies \frac{d\vec{v}}{dt}\cdot\vec{v}=\frac{1}{2}\frac{d}{dt}(\vec{v}\cdot\vec{v})$$

Substituting this back into the integral we get 

$$\begin{aligned}m\int_{t_i}^{t_f}\frac{d\vec{v}}{dt}\cdot \vec{v}dt &=\frac{m}{2}\int_{t_i}^{t_f}\frac{d}{dt}(\vec{v}\cdot\vec{v})dt\\&=\frac{1}{2}mv_{f}^{2}-\frac{1}{2}mv_{i}^{2}\end{aligned}$$

$$\implies \int_{\vec{r_i}}^{\vec{r_f}}F(\vec{r})\cdot d\vec{r}=\frac{1}{2}mv_{f}^{2}-\frac{1}{2}mv_{i}^{2}$$

I definitely abused some notation by leaving out the proper symbol for a line integral but this eludes to something pretty big. On the LHS we have a line integral, but on the right hand side we had an integral that only depended on the endpoints and gives us a scalar result. If you know a bit of vector calc (notes coming to your local site soon), this means we can rewrite the force $\vec{F}$ as a gradient of a vector field say $\nabla U$ that we call the potential energy (this also aludes to some very cool geometric features of our theory) and the idea of a path independent process which will remain prevelant in our study of classical mechanics. 

This is where physics and math kind of diverge. Because this integral only measures differences in $U$ we can arbitrarily choose the our poential energy function and do things like defining $U(\infty)=0$ for some forces. So defining the result of the integral as $U(r_i)-U(r_f)$ or simply making $F=-\nabla U$ is completely allowed. Gotta love physics making our lives easier.

Our next magic trick will be using the fact we just derived. We rewrite the force as $\vec{F}=-\nabla U$ and integrate once again

$$\int_{\vec{r_i}}^{\vec{r_f}}F(\vec{r})\cdot d\vec{r}=\int_{\vec{r_i}}^{\vec{r_f}}\nabla U(\vec{r})\cdot d\vec{r}=U(\vec{r_i})-U(\vec{r_f})$$

We then recall the work-energy theorem from above we can equate the two integrals and get 

$$K_f-K_i=U_i-U_f$$

With a simple rearrangement we finally get 

$$K_f+U_f=K_i+U_i$$

This is known as the Conservation of Energy. If you couldn't tell, this is a massive. With this we can determine the dynamics of a system from some initial or final conditions, but this does beg the question. We know that the overall energy is conserved for a system, what about over time? Let's define the total energy $E$ as $K+U$, and then we'll take the time derivative of this

$$\begin{aligned}\frac{dE}{dt}&=\frac{d}{dt}(K+U)=\frac{d}{dt}\left(\frac{1}{2}m(\vec{v}\cdot\vec{v})+U(\vec{r})\right)=\frac{1}{2}m\frac{d}{dt}(\vec{v}\cdot\vec{v})+\frac{\partial U}{\partial \vec{r}}\frac{d\vec{r}}{dt}\\&= m\left(\frac{d\vec{v}}{dt}\cdot\vec{v}\right)+\frac{\partial U}{\partial \vec{r}}\frac{d\vec{r}}{dt}=\vec{v}\left(m\vec{a}+\frac{\partial U}{\partial\vec{r}}\right)=\vec{v}(\vec{F}-\vec{F})=0\end{aligned}$$

So the energy is conserved over time as well!

This should hopefully have been a more chill introduction to basic Newtonian mechanics suitable for a physics or math person to start thinking about generalized dynamics. 

Next we'll be going over the nitty gritty mathematical details of what we just talked about (definitely not enough for a course in the resprective math subjects.....that sounds like a good idea) and also give an introduction to the calculus of variations. 

However...we can still have some physical motivation for why we describe the math as such. If you've ever dropped anything it should be fairly obvious that it doesn't matter where you are when it drops, it will drop regardless. If you've ever hanged on monkey bars and dropped some ice cream you were holding it still dropped the same way AND the kid running across the way also saw it drop (they're not moving at close to the speed of light so $c=\infty$ for now) in the same way. This simple, albeit not the best, experiment on the isotropy of the universe shows us that the universe simply doesn't have a preffered direction. So things like a center of the universe doesn't make sense. 

We can formalize this idea in mathematics with the use of an affine space that we will call Galilean spacetime. Let's first define what this space is exactly 

If we have a vector space $V$ over a field $\mathbb{F}$ (we won't get into the subtleties of this as I'm kinda lying about using an arbitrary field but, for our porposes you can assume $\mathbb{F}=\mathbb{R}$), an affine space $\mathbb{A}$ is a set $A$ modelled with our vector space such that $\exists \phi$ such that $\phi:V\times \mathbb{A}\rightarrow \mathbb{A}$ with $x,y\in\mathbb{A}$ and $v\in V$ that has the following properties

$$y=\phi(v,x)$$
$$\phi(v,x)=x\implies v=0$$
$$\phi(0,x)=x$$
$$\phi(u+v,x)=\phi(u,\phi(v,x))$$

These properties look a bit like addition don't they? Following general notation used we'll instead use $\phi(v,x)=v+x=y$. This would of course make you think that $v=x-y$ but I have to remind you that this is unfortunately just notation, as we havent defined what subtraction is in $\mathbb{A}$. Also note that intuitively this has to be the case as we've made no refernce to any sort of origin in our affine space.

Instead what we can do is fix $x\in\mathbb{A}$ (i.e fix some sort of relative origin) and this will let us define our usual vector space operations. For instance how about addition?

$$y_1+y_2=\left((y_1-x)+(y_2-x)\right)$$

Scalar multiplication is defined similarly

$$ay_1=\left(a(y_1-x)\right)$$

It should be fairly clear that when we fix this "origin" $\mathbb{A} \cong V$. 

Great! Now that we've sort of unveiled the structure of affine spaces it makes sense to study functions on them, mainly understanding transformations from one affine space to another. 

From linear algebra we know that the most general linear transformations say $f:V\rightarrow U$
