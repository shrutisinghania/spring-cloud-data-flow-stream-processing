# spring-cloud-data-flow-stream-processing
 Building on top of Baeldung's example (https://github.com/eugenp/tutorials/tree/master/spring-cloud-data-flow/spring-cloud-data-flow-stream-processing).



https://www.baeldung.com/spring-cloud-data-flow-stream-processing



https://dataflow.spring.io/docs/installation/local/manual/





strt skipper then server, followed by shell
 eg - java -jar spring-cloud-skipper-server-2.3.0.BUILD-SNAPSHOT.jar


UI for shell: http://localhost:9393/dashboard/#


Enter following cmnds in shell:


app register --name time-source --type source --uri maven://org.ilrs:time-source:0.0.1-SNAPSHOT

app register --name time-processor --type processor --uri maven://org.ilrs:time-processor:0.0.1-SNAPSHOT

app register --name log-sink --type sink --uri maven://org.ilrs:log-sink:0.0.1-SNAPSHOT

stream create --name time-to-log --definition 'time-source | time-processor | log-sink'

stream deploy --name time-to-log



check in skipper cmd where are the log files created - somewhere like - C:\Users\ss067504\AppData\Local\Temp\1586439371025\time-to-log.log-sink-v1