# Parameters

``parallelism`` -> how many tasks in one time can run
``completios`` -> how many tasks in job queue
``backoffLimit`` -> how many time job try to end tasks
``activeDeaflineSeconds`` -> how many time job has to finish full of taks

# Command

``kubectl logs -f -l job-name=<job_name>`` -> Show logs defined joba

``kubectl describe jobs/<job_name>`` ->	Show advance information about defined job