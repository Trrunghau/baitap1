l1=5;l2=4;
for t=-1:0.02:1
    x=8*sin(t)*cos(t)*log(abs(t));
    y=8*sqrt(abs(t))*cos(t);
    c2=(x^2+y^2-l1^2-l2^2)/(2*l1*l2);
    s2=sqrt(abs(1-c2^2));
    t2=atan2(s2,c2);
    c1=x*(l1+l2*c2)+y*l2*s2;
    s1=y*(l1+l2*c2)-x*l2*s2;
    t1=atan2(s1,c1);
    px=l1*cos(t1)+l2*cos((t1+t2));
    py=l1*sin(t1)+l2*sin((t1+t2));
    subplot(2,1,1);plot(t,t1*180/3.14,'m*',t,t2*180/3.14,'b+','linewidth',4);
    legend('t1','t2');
    hold on
    subplot(2,1,2);
    plot(px,py,'r*');
    hold on
end
