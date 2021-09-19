import math  

 def f(x):  

  

    return 4*x**4-4*x**3+2*x**2-3*x-9  

 def df(x):  

  

    return 16*x**3-12*x**2+4*x-3  

 def df2(x):  

  

    return 48*x**2-24*x+48  

 def mn(a,b,eps):  

  

    if f(b)*df(b)<0:  

  

        x=b   

  

    else:   

  

        x = a   

  

    h=f(x)/df(x)  

  

    x=x-h  

  

    if abs(h)<=eps:  

  

        print(x)  

  

    else:  

  

        h=f(x)/df(x)  

  

        x=x-h  

  

    return x  

 print (mn(-2,2,0.001))  

  

  def combine_method(a,b,eps):  

  

    if (df(a)*df2(a))<0:  

  

       a0=b;  

       b0=a;  

  

    else: 

        a0 = b 

        b0 = a 

  

    xp1=a0 

  

    xp2=b0 

  

    xn1 = xp1 - f(xp1)*(xp2-xp1)/(f(xp2)-f(xp1)); 

  

    xn2 = xp2 - f(xp2)/df(xp2); 

  

    xp1 = xn1; 

  

    xp2 = xn2; 

  

   while (xp2-xp1) > eps:  

  

       xn1 = xp1 - f(xp1)*(xp2-xp1)/(f(xp2)-f(xp1));  

  

       xn2 = xp2 - f(xp2)/df(xp2); 

  

       xp1 = xn1; 

  

       xp2 = xn2;  

  

  

    x = (xp1 + xp2)/2;   

  

    return x   

  

   

  

  print('Combine_method: ')  

 print(combine_method(-2,2,0.001))  

  

 def hord_method(a,b,e): 

    if f(a) * df(a) > 0: 

        x0 = a  

        xi = b  

    else: 

        x0 = b  

        xi = a  

         

    xi1 = xi - (((xi - x0) * f(xi))/ (f(xi) - f(x0))) 

     

    if math.fabs(xi1 - xi) > e:  

        xi = xi1 

        xi1 = xi - (((xi - x0) * f(xi)) / (f(xi) - f(x0))) 

 else: 

        f(xi1) 

    print(xi1) 

print("Root using the hord method:") 

hord_method(-2,2,0.001) 