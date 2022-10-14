### Task 6kyu:

Digital root is the recursive sum of all the digits in a number.
Given n, take the sum of the digits of n. If that value has more than one digit, continue reducing in this way until a single-digit number is produced. 
The input will be a non-negative integer.


[Task link](https://www.codewars.com/kata/541c8630095125aba6000c00/train/java)

#### Solution:
```
public class DRoot {
  public static int digital_root(int n) {
    return (n - 1) % 9 + 1;
    }
}
```

#### Fav solution:
```
public class DRoot {
  public static int digital_root(int n) {
    return (n - 1) % 9 + 1;
    }
}
```

#### Comment:
Thanks to number theory for defining the digital root and interpreting it. 


### Task 7kyu:

Take an integer n (n >= 0) and a digit d (0 <= d <= 9) as an integer.
Square all numbers k (0 <= k <= n) between 0 and n.
Count the numbers of digits d used in the writing of all the k**2.
Call nb_dig (or nbDig or ...) the function taking n and d as parameters and returning this count.

[Task link](https://www.codewars.com/kata/566fc12495810954b1000030/train/java)

#### Solution:
```
class CountDig
{
    public static int nbDig(int n, int d)
    {
        int c=0;
        for(int i=0;i<=n;i++)
        {
            int p=i*i;
            if ((p==0) && (d == 0)){ c++;}
            while(p!=0)
            {
                int l;
                l=p%10;
                if(l==d){
                    c++;
                }
                p=p/10;
            }
        }
        return c;
    }
}
```

#### Fav solution:
```
public class CountDig {
    
    public static int nbDig(int n, int d) {
        int c = 0;
        for (int i = 0; i < n + 1; i++) {
          int temp = i * i;
          while (true) {
            if (temp % 10 == d) c++;
            if ((temp /= 10) == 0) break;
          }
        }
        
        return c;
    }
}
```

#### Comment:
There were incomprehensible decisions. The latter repeats the idea of my solution, but written more accurately.
