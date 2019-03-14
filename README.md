# medio-curso-servo.-
parte practica


function dxdt = mariposa(t, x)
    a = 10;
    b = 28;
    c=8/3;
   
    x1=x(1);
    x2=x(2);
    x3=x(3);
    dxdt=[a*(x2-x1); x1*(b-x3)-x2; x1*x2-c*x3];
end

function [t, x] = call_mariposa()
    tspan = [0 100];
    x0 = 0;
    y0 = -1;
    z0 = -1;
    CI = [x0; y0;z0];
    [t, x] = ode15s(@mariposa,tspan, CI);
end
