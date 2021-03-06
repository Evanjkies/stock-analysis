# Stock-Analysis
## Overview of Project
The original goal of this project was to establish a macro that would pull from a listing of stocks and accumulate the volumes traded associated with each one on a seperate worksheet, as well as record the return as a percentage. Once a functional macro was established the new goal was to take a macro that was already established as functional, and refactor it to the point where it would have an easier time if were ever to be applied to a larger group of stocks and subsequent data.

## Results
In the original macro, the way it was looped forced the computer to go back and forth between locating a value for the volume of a particular stock, and adding it to the total for that stock's volume on the All Stocks Analysis worksheet. The back and forth nature of the loop caused it to perform slowly. The below images are the times for how long it took the macro to perform the analysis on each of the two years being pulled from.

![Original_All_Stocks_Run_2017](https://user-images.githubusercontent.com/107013312/175454898-62a33a60-9ac2-4e55-8e96-9ee37e9f38c3.png)

![Original_All_Stocks_Run_2018](https://user-images.githubusercontent.com/107013312/175454906-f6604090-c561-4a86-aaa6-97d743c6e261.png)

To imporve the times, which in turn will allow the macro to handle larger quantities of data, it needed to be refactored. This was done by implementing an index *tickerIndex = 0* for the ticker names given to each stock, and creating an array for the three necessary outputs using *Dim tickerVolumes(12) As Long*, *Dim tickerStartPrices(12) As Single*, *Dim tickerEndPrices(12) As Single* . Using the index and the array the data that we need for the All Stocks Analysis worksheet and can be looped through more efficiently. The 'for' loop used is very similar to the one in the original macro, except instead of looping through the original source of data, it loops through the arrays. Below are the images of the times for how long ittook the macro for each year after the changes had been made.

![VBA_Challenge_2017](https://user-images.githubusercontent.com/107013312/175458623-21cfdee5-7650-4944-9532-b0a71fc248b4.png)

![VBA_Challenge_2018](https://user-images.githubusercontent.com/107013312/175458630-fc6a77ba-103a-4fa3-8a6e-94d40c8604d2.png)

## Summary
The macro performed at a much faster rate after the refactoring. Both years performed at a nearly 10x more efficient rate, and this is an obvious advantage of rafactoring. A more efficient piece of code allows for more potential in terms of what can be processed. If the objective was to develop a macro that was meant to handle every open and close of every stock of the entire market, then the refactored code would perform at a higher rate than the original macro. This is not to overlook the disadvatage of refactoring code. There is truth to the phrase "if it ain't broke, don't fix it" and it can be found here. Refactoring code risks compromising the original code's functionality. The original macro that was written performed exactly as it needed to, and in an attempt to improve it, it seems entirely possible that it could have been compromised. Also, the time consuming nature of the task should be considered as a disadvantage. The time devoted to refactoring code could end up negating the amount of time saved by the refactored code performing it's function.    
