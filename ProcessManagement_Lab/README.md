#ToDo 4a:#

For this portion of the ToDo, I mostly followed the instructions in the ToDo and considered the following cases:

1. Process still alive and previous job has completed
2. Process still alive and previous job is still in progress
3. Process is not alive and previous job is done
4. Process is not alive and previous job is still in progress

For 1, because the job has completed, I assigned a new job to that child process.
As for 2 and 4, because the process is not alive/prematurely terminated, I used the method which you suggested to revive it which was to
run a fork and directed the child to the job_dispatch() function again

I put all this in a while loop that breaks after ascertained that all the jobs have been run, no more content in the input file

#ToDo 4b:#

In order to terminate all the workers that are currently alive, I took the following steps:
1. Loop through each process with a for loop
2. For each process, we check 2 things - If the child is alive and if it is running a job
3. If alive and not running a job, reset the duration and status and set the task type to 'z' which represents a termination type job
4. If it is still running a job, we decrement the counter value, waiting for the process to finish running the job
4. Lastly, I updated the semaphore in sem_jobs_buffer[] since I am done with it

