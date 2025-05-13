# Exp.No:40  
## APPLICATIONS OF QUEUE

---

### AIM  
To write a Python program to implement CPU Process Scheduling using a queue.

---

### ALGORITHM  

1. Start the program.  
2. Define the function `CalculateWaitingTime(at, bt, N)`.  
3. Initialize a list `wt` of size `N` with all values set to 0.  
4. Set `wt[0] = 0` for the first process.  
5. Print the table header: "P.No.", "Arrival Time", "Burst Time", "Waiting Time".  
6. Print the values for the first process.  
7. For each process from index `1` to `N-1`:  
   - Calculate `wt[i] = (at[i - 1] + bt[i - 1] + wt[i - 1]) - at[i]`.  
   - Print the process number, arrival time, burst time, and waiting time.  
8. Initialize `total_waiting_time = 0`.  
9. Add up all waiting times.  
10. Calculate average waiting time as `average = total_waiting_time / N`.  
11. Print the average waiting time.  
12. Get burst times as input from the user for 5 processes.  
13. Call `CalculateWaitingTime()` with `at`, `bt`, and `N`.  
14. End the program.

---

### PROGRAM  

```

def findWaitingTime(processes, n, bt, wt):
	wt[0] = 0
	for i in range(1, n ):
		wt[i] = bt[i - 1] + wt[i - 1]

def findTurnAroundTime(processes, n,
					bt, wt, tat):

	for i in range(n):
		tat[i] = bt[i] + wt[i]

def findavgTime( processes, n, bt):

	wt = [0] * n
	tat = [0] * n
	total_wt = 0
	total_tat = 0

	findWaitingTime(processes, n, bt, wt)

	findTurnAroundTime(processes, n,
					bt, wt, tat)

	print( "Processes Burst time " +
				" Waiting time " +
				" Turn around time")

	
	
	for i in range(0,n):
	    total_wt+=wt[i]
	    total_tat+=tat[i]
	    print(" "+str(i+1)+"   "+str(bt[i])+"  "+str(wt[i])+"    "+str(tat[i]))
	
		
	
	print( "Average waiting time = "+
				str(total_wt / n))
	print("Average turn around time = "+
					str(total_tat / n))

if __name__ =="__main__":
	
	processes = [ 1, 2, 3]
	n = len(processes)

	t0=int(input())
	t1=int(input())
	t2=int(input())
	burst_time = [t0,t1,t2]

	findavgTime(processes, n, burst_time)

```

### OUTPUT

![image](https://github.com/user-attachments/assets/739fde2e-152e-4ce6-adc6-3b07cdc4ea82)

### RESULT

Thus, the python program to implement CPU Process Scheduling using a queue has been executed and verified successfully.
