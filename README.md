# sock-merchant-code-problem-and-java-solution
hacker rank problem statement
John works at a clothing store. He has a large pile of socks that he must pair by color for sale. Given an array of integers representing the color of each sock, determine how many pairs of socks with matching colors there are.

For example, there are  socks with colors . There is one pair of color  and one of color . There are three odd socks left, one of each color. The number of pairs is .

Function Description

Complete the sockMerchant function in the editor below. It must return an integer representing the number of matching pairs of socks that are available.

sockMerchant has the following parameter(s):

n: the number of socks in the pile
ar: the colors of each sock
Input Format

The first line contains an integer , the number of socks represented in .
The second line contains  space-separated integers describing the colors  of the socks in the pile.

Constraints

 where 
Output Format

Return the total number of matching pairs of socks that John can sell.

Sample Input

9
10 20 20 10 10 30 50 10 20
Sample Output

3
Explanation

sock.png

John can match three pairs of socks.

*/////////////////////////////////////////////////////////////////////////////////////////*///////////////////////


package socks;


import java.util.Scanner;

public class socks{
	
      int search(int ser,int n,int d[])
    {
    	  int ret=5;
        for(int k=0;k<n;k++)
        {
            if(d[k]==ser)
            {
                ret=1;
            }
         
        }
        if(ret==1)
        {
        return 1;
        }
        else
        {
        return 0;
        }
        	
    }
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        int a[]=new int[n];
        int count=1,final_value=0,temp=0,ret=0,temp1=0;
        int analyse[]=new int[n];
        socks s=new socks();
        int div=0;
    
        for(int i=0;i<n;i++)
        {
         a[i]=sc.nextInt();   
         analyse[i]=0;
        }

        for(int j=0;j<n;j++)
        {
           
            for(int h=j+1;h<n;h++)
            {
            	 temp=a[j];
                 temp1=a[j+1];

            	  ret=s.search(temp,n,analyse);

                 if(ret==0)
                 {
                    
                if(a[j]==a[h])
                {
                    count++;
                }
                 
                 }
                
            }
            div=count/2;

            final_value=final_value+div;
            analyse[j]=a[j];


      
  	   int ret1=s.search(temp1,n,analyse);

            if(ret1==1)
            {
            	count=0;
            }
            else
            {
            	count=1;
            }


        }
      
        System.out.println(final_value);
    }
}
