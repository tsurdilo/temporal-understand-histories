# Temporal Understanding Workflow Histories Workshop

## Chapter 1

### What is execution history?

### Events created based on defined apis

https://github.com/temporalio/api/blob/master/temporal/api/enums/v1/event_type.proto

### Why is it important?

#### For wf exec
"blueprint" of your workflow execution
contains events "in order"
each "wf exec update" can be composed of multiple events in history

- it helps communicate current wf state to your workers
- its used internally for sdks for deterministic replay
    -  for example LA or versioning, side effects workers tell itself about
it so it can be used during replay
- it contains events generated by server (for example wf timeouts/termination/etc)
- it also contains events that are written in correspondence of 
client and worker commands to the server - https://github.com/temporalio/api/blob/master/temporal/api/command/v1/message.proto#L216

- has limitations (more on this in another section :) )


#### For users
- can be used to 
    - understand your wf execs (progress and current state) 
      regardless of the programming language used
    - audit trail
    - debug / troubleshoot (which this workshop focuses on)
    - testing - WorkflowReplayer
    - improve performance and architecture

### Where is it stored?
temporal db
visibility???

### How long is it available?
retention period
...archival???

### How to obtain it
tctl
sdk apis
web ui

### Limitations?

- 50K/50MB
- https://docs.temporal.io/kb/temporal-platform-limits-sheet

## Chapter 2
.... add here...

## Chapter 3 - Activities

- pending activities
- local activities
- ActivityTaskScheduled but not started (.....)
- Timeouts and Retries
- heartbeat timeouts
- timeout types (StartToClose.....) ActivityTaskFailed

## Chapter 4 - Child Workflow

## Chapter 5 - Timers 

- wofklow.sleep
- workflow.timer
- await with timeout
- await w/o timeout

## Chapter 6 - Cron
- firstWorkflowTaskBackoff

## Chapter 7 - Fixing errors / issues

- WorkflowTaskFailed 
- Non-deterministic error + versioning
- How to reset
- 





