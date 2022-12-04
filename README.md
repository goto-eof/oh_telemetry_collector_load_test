### OH Telemetry Collector load test

OH telemetry collector load test was developed for testing the application workload in order to make a comparison between the POC in Java and the one in Rust.

The application for load test comparison are the following:

- [oh_telemetry_collector_server_rust](https://github.com/goto-eof/oh_telemetry_collector_server_rust)
- [oh_telemetry_collector_server_java](https://github.com/goto-eof/oh_telemetry_collector_server_java)

(Remember first to run both docker containers: the POC developed in Rust and the one developed in Java)

The test result is under the reports directory. 

A meangfull value is the P95 percentile. It means that 95% of all our request had a response time equal or less than the value in the report. So that less is better.

#### Install packages

```bash
npm install
```

#### Run artillery for rust API and generate report

```bash
npm run rust
```

#### Run artillery for java API and generate report

```bash
npm run java
```

#### Run artillery for both, rust and java projects, and generate reports

```bash
npm run java && npm run rust
```
