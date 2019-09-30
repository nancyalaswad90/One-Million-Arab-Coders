

# Android-Development-Track Certification and Instructions



![image](https://user-images.githubusercontent.com/36210723/65849133-bc266600-e351-11e9-9fa0-154a4db1fd5d.png)



# Instructions  lab (1 )

Given that you have five input values and "average" method, calculate the average value for the five input values inside the average method and return it.

Note: average is the total summation of the values divided by its count.

public class MyCalculator {

    int input1 = 10;
    int input2 = 20;
    int input3 = 30;
    int input4 = 40;
    int input5 = 50;
 float averag;
    

    public float average() { 

    float average = (input1 +input2 +input3 +input4 +input5) /5;
        
         return (float) average;
    }
    
   
}



# My calculator lab (2 )


Description:

In this lab, you should create a calculator with its basic functions.

Create a calculator class which has sum, subtract, division, and multiply methods, all of them take two int parameters and return the resulted int.

Example: When the sum method is called as sum(5,6), it should return 11 which is the sum of 5 and 6

## Instructions

Create a calculator class which has sum, subtract, division, and multiply methods, all of them take two int parameters and return the resulted int.



// TODO create class MyCalculator with sum, divid, subtract, multiply
class MyCalculator {
    
    public int sum(int x,int y){
        int n = x + y;
        return n;         
    }
    
    public int divid(int x,int y){
        int n = x / y;
        return n;         
    }
    
    public int subtract(int x,int y){
        int n = x - y;
        return n;         
    }
    
    public int multiply(int x,int y){
        int n = x * y;
        return n;         
    }
}


