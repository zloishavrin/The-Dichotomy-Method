# The-Dichotomy-Method
Finding the root of an equation using the Dichotomy method.

Finding the root by the method of half division. Used to refine the root of the equation f(x)=0 with a given accuracy ε. 

Description of the algorithm:
1) Separate the roots. Let the function f(x) be continuous on the interval [a0,b0]. And we know that on [a0,b0] there is a single root of the equation f(x)=0. Then by virtue of continuity of f(x), the inequality takes place: 
f(a0)*f(b0)<0.
2) Let us divide the segment [a0,b0] in two by point c0=(a0+b0)/2. If f((a0+b0)/2) = 0, then c0 = (a0+b0)/2 is the root of the equation.  If f((a0+b0)/2) ≠ 0 then choose the segment [a0;c0] or [c0;b0] on the ends of which f(x) takes values of different signs. For this purpose we introduce the following notations:
if f(a0)*f(c0)>0 then a1=c0, and if f(a0)*f(c0)<0 then a1=a0,
If f(b0)*f(c0)>0 then b1=c0, and if f(b0)*f(c0)<0 then b1=a0.
3) Divide the remaining segment [a1,b1 ] in half and repeat the above system of notations. For arbitrary k-th division we have:
c(k) = (a(k) + b(k)) / 2, k = 1, 2, ...,
a(k+1) = c(k) if f(a(k))*f(c(k))>0 or a(k+1)=a(k) if f(a(k))*f(c(k))<0,
b(k+1) = c(k) if f(b(k))*f(c(k))>0 or b(k+1)=b(k) if f(b(k))*f(c(k))<0.
4) The algorithm terminates when b(k)-a(k)< ε. Otherwise the third point is repeated.

The advantage of this method is its simplicity and reliability, besides the algorithm converges for any continuous f(x).

The written code applies the standard mathematical operations (+,-,*,/), the trigonometric functions (sin,cos,ctg,tg), the natural and decimal logarithm (ln,lg) and some other functions (abs - absolute value, cbrt - cube root, sqrt - square root and exp - exponent). All arguments of these functions must be specified in parentheses (e.g., ctg(x)). If you don't have enough of these functions, you can add them inside the toMath function in the js-file.

The toMath function turns mathematical functions into js-functions of the built-in Math object. When adding functions, keep in mind that the original code in the arcsin function will replace 'sin' with Math.sin. Another thing to keep in mind when adding functions is that for some math functions there are no methods in built-in Math object - in such cases, you should use inverse functions or any other conversion of one function to another. This is what is done with the cotangent function in the original code. The cotangent is the inverse of the tangent function, hence ctg(x) = 1/tg(x).
