**PRACTISE QUESTION Lvl 2 —-------\> PRAGALYA K**

**1.Write a C program to print all natural numbers from 1 to n. – using while loop**

\#include\<stdio.h\>  
int main(){  
    int num;  
    scanf("%d",\&num);  
    for(int i=0;i\<=num;i++)  
    printf("%d\\n",i);  
    return 0;  
    }

**2.Write a C program to print all natural numbers in reverse (from n to 1). – using a while loop.**

\#include\<stdio.h\>  
int main(){  
    int num;  
    scanf("%d",\&num);  
    for(int i=0;i\<=num;i++)  
    printf("%d\\n",num-i);  
    return 0;  
    }

**3.Write a C program to print all alphabets from a to z and using A to Z – using while loop**

\#include\<stdio.h\>  
int main(){  
    char a,b;  
    a \= 'A';  
    b \='a';  
    while(a\<='Z'){  
        printf("%c ",a);  
        a++;  
    }  
    printf("\\n");  
    while(b\<='z'){  
        printf("%c ",b);  
        b++;  
    }  
    return 0;  
    }

**4.Write a C program to print all even numbers between 1 to 100\. – using while loop**

\#include\<stdio.h\>  
int main(){  
    int a;  
    while(a\<=100){  
        if(a%2==0)  
          printf("%d\\n",a);  
    a++;  
    }  
    return 0;  
    }

**5.Write a C program to print all odd numbers between 1 to 100\.**

\#include\<stdio.h\>  
int main(){  
    int a;  
    while(a\<=100){  
        if(a%2\!=0)  
          printf("%d\\n",a);  
    a++;  
    }  
    return 0;  
    }

**6.Write a C program to find the sum of all natural numbers between 1 to n.**

\#include\<stdio.h\>  
int main(){  
    int a=1,num,sum=0;  
    scanf("%d",\&num);  
    while(a\<=num){  
         sum \+= a;  
         a++;  
    }  
    printf("%d\\n",sum);  
    return 0;  
    }

**7.Write a C program to find the sum of all even numbers between 1 to n.**

\#include\<stdio.h\>  
int main(){  
    int a=0,num,sum=0;  
    scanf("%d",\&num);  
    while(a\<=num){  
         if(a%2==0){  
         sum \+= a;}  
         a++;  
    }  
    printf("%d\\n",sum);  
    return 0;  
    }

**8.Write a C program to print a multiplication table of any number.**

\#include\<stdio.h\>  
int main(){  
    int a=1,num,end,val;  
    scanf("%d",\&num);  
    scanf("%d",\&end);  
    while(a\<=end){  
         val \=num\*a;  
         printf("%d\\n",val);  
         a++;}  
    return 0;  
    }

**9.Write a C program to count the number of digits in a number.**

\#include\<stdio.h\>  
int main(){  
    int count=0,num,remi;  
    scanf("%d",\&num);  
    while(num\!=0){  
        remi=num%10;  
        num/=10;  
        count++;  
    }  
    printf("%d",count);  
    return 0;  
    }  
**10.Write a C program to find the first and last digit of a number and their sum.**

\#include\<stdio.h\>  
int main(){  
    int count=0,num,remi,dup,sum;  
      
    scanf("%d",\&num);  
    dup \= num;  
    remi=dup%10;  
    while(num\>10){  
        num/=10;  
    }  
    sum \= num+remi;  
    printf("%d ",num);  
    printf("%d",remi);  
    printf("\\n");  
    printf("%d",sum);  
    return 0;  
    }

**12.Write a C program to calculate the sum of digits of a number.**

\#include\<stdio.h\>  
int main(){  
    int count=0,num,remi,dup,sum=0;  
    scanf("%d",\&num);  
    while(num\!=0){  
        remi \= num%10;  
        sum+=remi;  
        num/=10;  
    }  
    printf("%d",sum);  
    return 0;  
    }

**13.To find if it is a leap year or not , if it is a leap year then find the next consecutive leap year by getting the value from the user.**

\#include\<stdio.h\>  
int main(){  
    int year,count=0,end\_val;  
    scanf("%d",\&year);  
    if(year%4==0 && year%100\!=0 ||(year%400)){  
        scanf("%d",\&end\_val);  
        while(end\_val){  
            count \= year \+ 4;  
            year \= count;  
            end\_val--;  
            printf("%d\\n",count);  
        }  
    }  
    else  
    printf("not a leap year"); }

**14.Write a C program to enter a number and print its reverse.**

\#include\<stdio.h\>  
int main(){  
    int num1,remi,digi;  
    scanf("%d",\&num1);  
    while(num1\!=0){  
        remi=num1%10;  
        digi=(digi\*10)+remi;//  \*10 operation is used to shift the digits one place to the left  
        num1/=10;  
    }  
    printf("%d",num1);  
    printf("%d",digi);  
    }  
      
**15.Write a C program to check whether a number is palindrome or not.**

\#include\<stdio.h\>  
int main(){  
    int num1,remi,digi=0,original;  
    scanf("%d",\&num1);  
    original \= num1;  
    while(num1\!=0){  
        remi=num1%10;  
        digi=(digi\*10)+remi;  
        num1/=10;  
    }  
    if(digi==original){  
        printf("Palindrome %d",original);  
    }  
    else  
     printf("Not a palindrome %d",original);

    }

**16.Write a C program to find the frequency of each digit in a given integer.**

\#include\<stdio.h\>  
int main() {  
    int num, count\[10\] \= {0}, rem;  
    scanf("%d", \&num);  
    while (num \!= 0\) {  
        rem \= num % 10;  
        count\[rem\]++;  
        num /= 10;  
    }  
    // Print the frequency of each digit  
    printf("Frequency of digits:\\n");  
    for (int i \= 0; i \< 10; i++) {  
        if (count\[i\] \> 0\) {  
            printf("Digit %d: %d\\n", i, count\[i\]);  
        }  
    }  
    return 0;}

**17.If we are getting an input and printing it’s cube . Then we are getting other input from the user such as from input how many number’s cube we need. And print its cube.**

\#include\<stdio.h\>  
\#include\<math.h\>  
int main(){  
    int num,end,val;  
    scanf("%d %d",\&num,\&end);  
    for(int i=0;i\<=end;i++){  
        val=pow(num,3);  
        num++;  
        printf("%d\\n",val);  
    }  
    return 0;  
    }

**18.Write a C program to enter a number and print it in words.**

\#include \<stdio.h\>  
  void printName(int num){  
        switch(num){  
            case 0:  
            printf("zero");  
            break;  
            case 1:  
            printf("one");  
            break;  
            case 2:  
            printf("two");  
            break;  
            case 3:  
            printf("three");  
            break;  
            case 4:  
            printf("four");  
            break;  
            case 5:  
            printf("five");  
            break;  
            case 6:  
            printf("six");  
            break;  
            case 7:  
            printf("seven");  
            break;  
            case 8:  
            printf("eight");  
            break;  
            case 9:  
            printf("nine");  
            break;  
        }  
    }  
int main(){  
    int num,remi,digit=0;  
    scanf("%d",\&num);  
    while(num\!=0){  
        remi=num%10;  
        digit=(digit\*10)+remi;  
        num/=10;  
    }  
    while(digit\!=0){  
        remi=digit%10;  
        printName(remi);  
        digit/=10;  
    }  
}

**19.find the GCD .**

\#include \<stdio.h\>  
int main() {  
    int num1,num2,i,gcd;  
    scanf("%d %d",\&num1,\&num2);  
    for(i=1;i\<=num1 && i\<=num2;++i){  
        if(num1%i==0 && num2%i==0)  
            gcd=i;  
        }  
        printf("%d\\n",gcd);  
    return 0;  
}

**20\. Program To Increment By 1 To All The Digits Of A Given Integer**  
   
\#include\<stdio.h\>  
int main(){  
    int num,remi=0,digit,position=1;  
    scanf("%d",\&num);  
    while(num\!=0){  
        remi \= num%10;  
        remi++;  
        if(remi==10)  
          remi=0;  
        digit \+= remi \* position;  
        position \*= 10;  
        num /= 10;  
    }  
    printf("%d",digit);  
}

**21.To find if the given number is odd/even. And print their respective range.**

\#include \<stdio.h\>  
int main() {  
    int num;  
    printf("Enter an integer: ");  
    scanf("%d", \&num);  
    if(num%2==0){  
        printf("%d\\n",num);  
        for(int i=2;i\<num;i+=2)  
         printf("%d\\n",i);  
    }  
else {  
 printf("%d",num);  
 for(int i=2;i\<num;i+=2)  
         printf("%d\\n",i);  
}  
    return 0;  
}

**22.Find the LCM and GCD** 

\#include \<stdio.h\>  
int main() {  
    int num1,num2,lcm,gcd,neu,deno,remi;  
    scanf("%d %d",\&num1,\&num2);  
    neu \= (num1\>num2)?num1:num2;  
    deno \= (num2\<num1)?num1:num2;  
    remi \= neu%deno;  
     while(remi\!=0){  
         neu \= deno;  
         deno=remi;  
         remi \= neu%deno;  
     }  
     gcd \= deno;   
     lcm \= (num1\*num2)/gcd;  
     printf("%d\\n",lcm);  
     printf("%d\\n",gcd);  
     return 0;  
}

**23\. Find the abundant number .(**

\#include\<stdio.h\>  
int main(){  
    int num,sum=0;  
    scanf("%d",\&num);  
    for(int i \=1;i\<=num/2;i++){  
        if(num%i==0){  
            sum+=i;  
        }  
    }  
    if(num \< sum){  
    printf("It's abundant number\\n");  
    printf("Abundance is %d",sum \- num);}  
    else  
    printf("Not a abundance number");  
}

**24.Find if the following is Automorphic number or not**

\#include \<stdio.h\>  
int main()  
{  
    unsigned long long  int num,square;  
    scanf("%llu",\&num);  
    square \= num\*num;  
    int flag \= 1;  
    while(num\!=0){  
        if(num%10 \!= square%10)  
        flag=0;

        num /=10;  
        square/=10;  
    }   
    if(flag==1){  
        printf("Automorphic");  
    }  
    else  
    printf("Not automorphic");  
}

**26.Write a C program to input the gas consumption in cubic meters and calculate the total cost according to the given conditions:**

* **For the first 50 cubic meters, Rs.0.75 per cubic meter.**  
* **For the next 100 cubic meters, Rs.1.00 per cubic meter.**  
* **For the next 150 cubic meters, Rs.1.25 per cubic meter.**  
* **For cubic meters above 300, Rs.1.50 per cubic meter.**  
* **Include a 10% tax on the final cost.**

**27.find the product of digits.**

\#include \<stdio.h\>  
int main() {  
    int num,rev=1,rem,digi;  
    scanf("%d",\&num);  
    while(num\!=0){  
    rem \= num%10;  
    rev \= rev\*rem;  
    num/=10;  
      
    }  
    printf("%d",rev);  
}

**28.To find the frequency of the number returns without loops**

\#include \<stdio.h\>  
int main()  
{  
    int n,digit,co0=0,co1=0,co2=0,co3=0,co4=0,co5=0,co6=0,co7=0,co8=0,co9=0;  
    scanf("%d",\&n);  
    while(n\!=0)  
    {  
        digit=n%10;  
        switch(digit)  
        {  
            case 0:  
            co0++;  
            break;  
            case 1:  
            co1++;  
            break;  
            case 2:  
            co2++;  
            break;  
            case 3:  
            co3++;  
            break;  
            case 4:  
            co4++;  
            break;  
            case 5:  
            co5++;  
            break;  
            case 6:  
            co6++;  
            break;  
            case 7:  
            co7++;  
            break;  
            case 8:  
            co8++;  
            break;  
            case 9:  
            co9++;  
            break;  
        }  
        n/=10;  
    }  
    if(co0\>0)  
    printf("0 count is %d\\n",co0);  
    if(co1\>0)  
    printf("1 count is %d\\n",co1);  
    if(co2\>0)  
    printf("2 count is %d\\n",co2);  
    if(co3\>0)  
    printf("3 count is %d\\n",co3);  
    if(co4\>0)  
    printf("4 count is %d\\n",co4);  
    if(co5\>0)  
    printf("5 count is %d\\n",co5);  
    if(co6\>0)  
    printf("6 count is %d\\n",co6);  
    if(co7\>0)  
    printf("7 count is %d\\n",co7);  
    if(co8\>0)  
    printf("8 count is %d\\n",co8);  
    if(co9\>0)  
    printf("9 count is %d\\n",co9);  
    return 0;  
}

**29\. To find the  digital sum of the given number.**

\#include \<stdio.h\>  
int main() {  
    int num, sum \= 0;  
    // Input the number  
    printf("Enter a number: ");  
    scanf("%d", \&num);  
    // Calculate the digital sum  
    while (num \> 0 || sum \> 9\) {  
        if (num \== 0\) {  
            num \= sum;  
            sum \= 0;  
        }  
        else {  
            sum \+= num % 10;  
            num /= 10;  
        }  
    }  
    printf("Digital sum: %d\\n", sum);  
    return 0;  
}

//The digital sum of 1234 is 1 \+ 2 \+ 3 \+ 4 \= 10\. Since 10 is a two-digit number, you repeat the process: 1 \+ 0 \= 1\. So, the digital sum of 1234 is 1\.  
The digital sum of 456 is 4 \+ 5 \+ 6 \= 15\. Since 15 is a two-digit number, you repeat the process: 1 \+ 5 \= 6\. So, the digital sum of 456 is 6\.

**30.To find if the number is a Narcissistic number or not ,** 

\#include\<stdio.h\>  
\#include\<math.h\>  
int main(){  
    int num,remi,digit=0,rev=0;  
    scanf("%d",\&num);  
    digit \= (int)(log10(num)+1);  
    printf("%d\\n",digit);  
    while(num1\!=0){  
        remi \= num1%10;  
        rev+=pow(remi,digit);  
        num1 /=10;  
    }  
    printf("%d\\n",rev);  
    if(num \== rev){  
        printf("It is a Narcissistic");}  
    else{   
    printf("It is not Narcissistic");  
    }  
}  
next pa  
**30.How to find the Next 5 Palindromes?**  
\#include \<stdio.h\>  
int reverse(int num) {  
    int rev \= 0;  
    while (num \> 0\) {  
        rev \= rev \* 10 \+ num % 10;  
        num /= 10;  
    }  
    return rev;  
}  
int main() {  
    int num, next\_palindrome, count \= 0;  
    // Input the number  
    printf("Enter a number: ");  
    scanf("%d", \&num);  
    // Find the next palindromes  
    while (count \< 5\) {  
        num++;  
        if (num \== reverse(num)) {  
            next\_palindrome \= num;  
              count++;  
            printf("Next palindromic sequence after %d: %d\\n", num \- 1, next\_palindrome);  
        }  
    }  
    return 0;  
}

**31\. Swapping the last number and first number and printing the whole number?**

\#include \<stdio.h\>  
\#include \<math.h\>  
int main()  
{                                                                 //input: 1234  
    int num,first,last,digit,swap;  
    scanf("%d",\&num);  
    last= num %10; //4  
    digit= (int)log10(num);  //3  
    first \= (int)num/pow(10,digit);                //1234 % 1000= 1  
    swap= last;                                            //4  
    swap\*=(int)pow(10,digit);                      //4\*1000=4000  
    swap+= (num % ((int)pow(10,digit)));   //1235%1000=234 this add to                                                                                                    //swap,so 4000+234=4234  
    swap-=num%10;                                   //1234 %10 \=4 sub this in swap so 4234-4=4230  
    swap+= first;                                         //4230+1=4231  
    printf("%d",swap);  
}

**32.Print the armstrong number.**

\#include\<stdio.h\>  
\#include\<math.h\>  
int main(){  
    int num,temp,remi,digit,ami,sum=0;  
    scanf("%d",\&num);  
    temp \= num;  
    digit \= (int)log10(num)+1;  
    while(num\!=0){  
        remi \= num%10;  
        ami \= pow(remi,digit);  
        sum+=ami;  
        printf("%d\\n",ami);  
        num/=10;  
    }  
    printf("The sum of the given number is %d\\n",sum);  
    if(num \== ami)  
     printf("");  
}

**33.Perfect number** 

\#include\<stdio.h\>  
int main(){  
    int a,sum=0,val;  
    scanf("%d",\&a);  
    for(int i=1;i\<a;i++){  
        if(a%i \== 0){  
           sum+=i;  
        }  
    }  
    printf("%d\\n",sum);  
    if(sum \== a)  
    printf("Perfect number");  
    else  
    printf("Not a perfect number");  
}

**34.Find if the given prime number factor or not?**

\#include \<stdio.h\>  
\#include \<math.h\>  
int main() {  
    int num, isComposite \= 0;  
    scanf("%d", \&num);  
    for (int i \= 2; i \<= sqrt(num); i++) {  
        if (num % i \== 0\) {  
            isComposite \= 1;  
            for (int j \= 2; j \<= sqrt(i); j++) {  
                if (i % j \== 0\) {  
                    isComposite \= 0;  
                    break;  
                }  
            }  
            if (isComposite \== 1\) {  
                printf("%d is a prime factor\\n", i);  
            }  
        }  
    }  
      
    if (\!isComposite && num \!= 1\) {  
        printf("%d is a prime number factor\\n", num);  
    }  
      
    return 0;  
}

**35.To find nth term, sum and fibonacci series.**

\#include\<stdio.h\>  
int main(){  
    int num,sum=0,res;  
    scanf("%d",\&num);  
    int a \=0;  
    int b= 1;  
    if(num\>0){  
        for(int i=1;i\<=num;i++){  
            sum+=a;  
        printf("%d ",a);  
        res \= a+b;  
        a=b;  
        b=res;  
        }  
    printf("the nth term is: %d\\n",a);  
    printf("the sum is %d",sum);  
    }  
    else  
    printf("Invalid Input");  
}

Or 

\#include \<stdio.h\>  
int main() {  
    int num, fib1 \= 0, fib2 \= 1, nextTerm;  
    scanf("%d", \&num);  
    printf("Fibonacci series up to %d: ", num);  
    printf("%d, %d, ", fib1, fib2);  
    nextTerm \= fib1 \+ fib2;  
    while (nextTerm \<= num) {  
        printf("%d, ", nextTerm);  
        fib1 \= fib2;  
        fib2 \= nextTerm;  
        nextTerm \= fib1 \+ fib2;  
    }  
    return 0;  
}

**36\. To  find if the given number is prime or not**

\#include\<stdio.h\>  
int main(){  
    int num,isPrime=1;  
    scanf("%d",\&num);  
    for(int i=2;i\<=num/2;i++){  
        if(num%i \== 0\)  
        isPrime \= 0;  
        break;  
    }  
if(isPrime \== 1 && num\>1)  
printf("Prime number %d",num);  
else  
printf("Not a prime number %d",num);  
}

**37\. To find the Factorial of the given number.**

\#include\<stdio.h\>  
int main(){  
    int num,fact=1;  
    scanf("%d",\&num);  
    for(int i=1;i\<=num;i++){  
        fact\*=i;  
    }  
    printf("%d",fact);  
}

**38\. Finding the sum in n-series** (n+nn+nnn…)

\#include \<stdio.h\>  
int main()  
{  
int num,temp,rem,digit=0,sum=0,n;  
scanf("%d",\&num);  
scanf("%d",\&n);  
temp=num;  
for(int i=0;i\<n;i++){  
  digit=(digit\*10) \+ temp;  
  sum+=digit;  
  if(i\!=n-1)  
  printf("%d \+ ",digit);  
  else  
  printf("%d",digit);  
}  
printf(" \= %d",sum);  
}  
     
**39.Print the odd/even value within the range.**

\#include \<stdio.h\>  
int main() {  
    int num;  
    printf("Enter an integer: ");  
    scanf("%d", \&num);  
    else if(num%2==0){  
        printf("%d\\n",num);  
        for(int i=2;i\<num;i+=2)  
         printf("%d\\n",i);  
    }  
else if {  
 printf("%d",num);  
 for(int i=2;i\<num;i+=2)  
         printf("%d\\n",i);  
}  
    return 0;  
}

**40.To find the next three number’s cubes.**

\#include \<stdio.h\>  
\#include \<math.h\>  
int main() {  
    int num1,power,temp;  
    scanf("%d",\&num1);  
    temp=num1;  
    for(int i=0;i\<=3;i++){  
        temp=num1+i;  
        power \= pow(temp,3);  
        printf("%d\\n",power);  
    }  
     return 0;  
}

**41\. Print the Harmonic series** 

\#include\<stdio.h\>  
int main(){  
    int num;  
    scanf("%d",\&num);  
    float sum \= 0.0;  
    for(int i=1;i\<=num;i++){  
        printf("1/%d\\n",i);  
        sum+=1/(float)i;  
    }  
    printf("%f",sum);  
}

**42.To check the next 5 prime numbers**

\#include \<stdio.h\>  
int is\_prime(int num){  
    if(num\<=1)  
    return 0;  
    for(int i=2;i\*i\<=num;i++){  
        if(num%i==0){  
            return 0;  
        }  
    }  
    return 1;  
}  
int main(){  
    int num;   
    scanf("%d",\&num);  
    int count \= 0;  
    while(count\<5){  
        num++;  
        if(is\_prime(num))  
        printf("%d\\n",num);  
        count++;  
    }  
}

**43\. Count the vowels ,consonants and number in the given string** 

\#include\<stdio.h\>  
int main(){  
    char a;  
    int vow=0,consta=0,num=0;  
    while((a \= getchar()) \!= '\\n'){  
    if(a\>='a' && a\<='z' || a\>='A' && a\<='z'){  
        if(a \=='a' ||a \=='e' ||a \=='i' ||a \=='o' ||a \=='u' ||a \=='A' ||a \=='E' ||a \=='I' ||a \=='O' ||a \=='U'){  
            vow++;  
        }  
        else if (\!(a \=='a' ||a \=='e' ||a \=='i' ||a \=='o' ||a \=='u' ||a \=='A' ||a \=='E' ||a \=='I' ||a \=='O' ||a \=='U'))  
           consta++;  
    }  
    else if(a\>='0' && a\<='9'){  
        num++;  
    }  
    }  
    printf("%d %d %d",vow,consta,num);  
}

**44\. How to find the nth term in Palindrome?**

\#include\<stdio.h\>  
int main(){  
    int num,digit=0,temp,remi;  
    printf("enter the n value: ");  
    scanf("%d",\&num);  
    for(int i=1;i\<=num;i++){  
        digit=0;  
        temp=i;  
        while(temp\!=0){  
        remi=temp%10;  
        digit=digit\*10+remi;  
        temp/=10;  
        }  
        if(i==digit){  
            printf("%d ",i);  
        }  
    }  
    return 0;  
}

**45\. The leap years and non-leap years are needed to be printed , it must be in the range of 1 decade.**

\#include \<stdio.h\>  
\#include\<math.h\>  
int main() {  
    int year;  
    scanf("%d",\&year);  
    int yr2 \= year;  
    int count1=0;  
    int count2 \= 0;  
    while(count1\<10){  
        year++;  
        if(((year%4==0)&&(year%100\!=0))||(year%400==0)){  
            printf("%d ",year);  
            }  
        count1++;  
    }  
    printf("\\n");  
    while(count2\<10){  
        yr2++;  
        if(\!((yr2%4==0)&&(yr2%100\!=0))||(yr2%400==0)){  
            printf("%d ",yr2);  
            }  
        count2++;  
    }  
    }

**46\.  Sum of digits excluding the first and last digits.**

\#include \<stdio.h\>  
\#include\<math.h\>  
int main()  
{  
    int n,d,sum=0;  
    scanf("%d",\&n);  
    int len=(int)log10(n)+1;           // len \=4  
    int l \= n%10;                           // l=1  
    n=n-l;                                     //2550  
    while(n\>10){  
        d \= n%10;  
        sum \= sum \+d;  
        n/=10;  
    }  
    printf("%d",sum);  
    return 0;  
}

Or 

\#include \<stdio.h\>  
\#include \<string.h\>  
int main()  
{  
   int num,rem=0,sum=0;  
   scanf("%d",\&num);  
   int temp \= num;  
   int last \= num%10;  
   while(num\!=0){  
     rem \= num%10;  
     num/=10;  
   }  
   int first \= rem;  
   rem \=0;  
   while(temp\!=0){  
     rem \= temp%10;  
     sum+=rem;  
     temp/=10;  
   }  
  int final \= sum-abs(first+last);  
  printf("%d ",sum);  
  printf("%d",final);  
}

**47\. The  6 digit number is given and we must produce the pair like(1st and 2nd digit).**

\#include \<stdio.h\>  
int main() {  
    int n;  
    scanf("%d", \&n);  
    int tot1, tot2, tot3;  
    int set1 \= 0, set2 \= 0, set3 \= 0, set4 \= 0, set5 \= 0, set6 \= 0;  
    int d;

    d \= n % 10;  
    set1 \= d;  
    n /= 10;

    d \= n % 10;  
    set2 \= d;  
    n /= 10;

    d \= n % 10;  
    set3 \= d;  
    n /= 10;

    d \= n % 10;  
    set4 \= d;  
    n /= 10;

    d \= n % 10;  
    set5 \= d;  
    n /= 10;

    d \= n % 10;  
    set6 \= d;  
    n /= 10;

    if (set6 \!= 0 && set5 \!= 0\) {  
        tot1 \= set6 \* set5;  
    } else {  
        printf("Invalid\\n");  
        return 0;  
    }  
    if (set4 \!= 0 && set3 \!= 0\) {  
        tot2 \= set4 \* set3;  
    } else {  
        printf("Invalid\\n");  
        return 0;  
    }  
    if (set2 \!= 0 && set1 \!= 0\) {  
        tot3 \= set2 \* set1;  
    } else {  
        printf("Invalid\\n");  
        return 0;  
    }  
    printf("%d %d %d\\n", tot1, tot2, tot3);  
    return 0;  
}  
