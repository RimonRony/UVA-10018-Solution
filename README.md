##UVA 10018 :: REVERS AND ADD

[What is the concept of the problem =: Here , you have to choose a number , then find out the reverse of the number . If the choosen number is same to the revers number then it is the palindrom number. So thats why , if the number is not palindrom first time , then you have to add the number with the revers of it which is number+revers . And doing it until you get the palindrom. ]

My solution hints::

for revers i just create a funtion named reverse . ok lets here is the solution (C++) ::

#include<iostream>
#include<cstdio>
#include<cmath>
using namespace std;
long long int revers(long long int n)

{
    long long int r ;
    long long int k = 0;
    while ( n != 0)
    {
        r = n % 10;
        k = k*10 + r;
        n = n/10;
    }
    return k;
}

int main ()
{
    long long int original, rv, n;
    int kase , kount;
    cin>>kase;
    for (int i=1; i<=kase; i++)
    {
        kount=0;
        cin>>n;
        while (1)
        {
            original = n;
            rv = 0 ;
            rv = revers(n);
            if ( rv ==n )
            {
                break;
            }
            else
            {
                n = rv + original;
                kount++;
            }
        }
        cout<<kount<<" "<<n<<endl;
    }
    return 0;
}

