# Parameters

``schedule: "* * * * *"`` -> time to start cronjob
``.spec.concurrencyPolicy: Allow`` -> to determine whether, if one job has not been terminated, another can? (default on)
``.spec.startingDeadlineSecond`` -> the maximum time it can take to try to restart the job
``startingDeadlineSecond: 60`` -> specifying that a job may start within 60 seconds of the scheduled start-up - in this case 60 seconds after the scheduled time