# Develop a new greedy algorithm to solve the job scheduling problem and analyze its efficiency and effectiveness in  Python.

def job_scheduling(jobs):
    # Sort jobs in decreasing order of deadlines
    sorted_jobs = sorted(jobs, key=lambda x: x[1], reverse=True)
    
    # Initialize variables
    schedule = []
    completion_time = 0
    
    # Iterate through jobs and schedule if feasible
    for job in sorted_jobs:
        processing_time, deadline = job
        if completion_time + processing_time <= deadline:
            schedule.append(job)
            completion_time += processing_time
    
    # Return schedule and number of missed deadlines
    num_missed = len(jobs) - len(schedule)
    return schedule, num_missed
