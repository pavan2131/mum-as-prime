# numm-as-prime
Express a num as sum of prime
 perform this task, a user-defined function is created to check prime number.

Example: Check Whether a Number can be Expressed as a Sum of Two Prime Numbers
#include <iostream>
using namespace std;

bool checkPrime(int n);

int main()
{
    int n, i;
    bool flag = false;

    cout << "Enter a positive  integer: ";
    cin >> n;

    for(i = 2; i <= n/2; ++i)
    {
        if (checkPrime(i))
        {
            if (checkPrime(n - i))
            {
                cout << n << " = " << i << " + " << n-i << endl;
                flag = true;
            }
        }
    }

    if (!flag)
      cout << n << " can't be expressed as sum of two prime numbers.";

    return 0;
}

// Check prime number
bool checkPrime(int n)
{
    int i;
    bool isPrime = true;

    for(i = 2; i <= n/2; ++i)
    {
        if(n % i == 0)
        {
            isPrime = false;
            break;
        }
    }

    return isPrime;
}
