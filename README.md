# Matlab-coding-files
%% I have attached the matlab coding file Related to power system for sample purpose. 
%% program for indices matrice A
disp('hello this is program for indices matrices')
disp(' ')
disp('please first draw tree diagram by yourself on paper')
disp('okay i will ask you few ques about your diagram to help you in finding A matrice')
disp(' ')
disp('enter the no of elements in your system without generator')
e=input('enter: ');
disp('enter no of buses in your system')
b=input('enter : ');
disp('enter no of generator in your system')
g=input('enter : ');
% A is called indices matrices
if g>0
    initial_node=0;
    totalnodes_no=b+1;
    e=e+g;
else
    initial_node=1;
    totalnodes_no=b;
end
A=zeros(e,totalnodes_no);

disp('Now I am ask ques about your tree diagram ')
for i=1:e
    x=num2str(i);
    disp([' element no. ',x])
    m=input('    is from node no. : ');
    n=input('        to  node no. : ');
    

if(g>0)    
    A(i,m+1)=+1;
    A(i,n+1)=-1;
end
if(g==0)
    A(i,m)=+1;
    A(i,n)=-1;
end

    
    
end
disp('your element node indices matrice')
disp('A^ =')
disp(A)
disp('  ')
disp('  ')

disp('your bus incidence matrice is')
disp('A=')
disp(A(1:e,2:totalnodes_no))

