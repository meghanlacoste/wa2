# wa2

using System;
using static System.Console;
using static System.Math;

namespace Assignment2
{
    class Program
    {
        static void Main(string[] args)
        {
           // for every base =< n-2 test
           // see if there are all equal numbers which it can be represented by 
           
           //You can find the rightmost digit of n represented in base b by evaluating n % b.
           // You can shift the number n one digit to the right in base by by n = n / b.
           //With a loop over these two operations, you can find all the digits of n in base b.
           
           WriteLine ("Enter positive integer: " );
           int n = int.Parse(ReadLine ());
           
      
      bool notDone = true;
      bool equal = true;
      int count =1; 
      
      // set the base for 1 less than the input number and iteratively decrease until 
      // the base is 2
      
        for (int b = n-1; b > 1; b--)
         {
            // creates temporary variable and keeps 'n' static
            int tempn = n;
            
            // reset variables for each new base
            count = 1;
            equal = true;
            notDone = true;
            
                  int origMod = tempn % b;
                  tempn /= b;
                  
                          while (equal && notDone)
                           {
                          
                            // finds new modulus
                            int newMod = tempn % b;
                            
                                
                                if (tempn == 0 ) 
                                {
                                
                                    notDone = false;
                                
                                }
                                 else if (newMod != origMod) 
                                {
                                
                                // the modules are not equal to eachother
                                equal = false;
                                
                                } 
                                else 
                                {
                                
                                // the modules are equal and the number is shifted to the right
                                 
                                  tempn /= b;
                                
                                  count ++;
                                
                                }// end else 
                            
                            } // end while
                            
                        if (count > 1 && equal)
                         {
                        
                        Write ( $"{n} in base 10 is " );
                        
                                while (count > 0) 
                                {
                                
                                    if (count == 1 ) 
                                    {
                                    
                                    Write ( $"{origMod}");
                                    
                                    count--;
                                    
                                    } 
                                    else
                                    {
                                
                                    Write ( $"{origMod},");
                                    
                                    count--;
                                    }
                                }
                        
                        WriteLine ($" in base {b}");
                    
                   
                   }// end if (equal)      
            
              
              }// end for loop
            
        
        

        } // end main method 
        
        
           
           
        }// end Program
    }// end namespace

