### OH Telemetry Collector load test

OH telemetry collector load test was developed for testing the applications workload. So that we can make a comparison between the POC in Java, Rust and TypeScript.

The applications are the following:

- [oh_telemetry_collector_server_rust](https://github.com/goto-eof/oh_telemetry_collector_server_rust)
- [oh_telemetry_collector_server_java](https://github.com/goto-eof/oh_telemetry_collector_server_java)
- [oh_telemetry_collector_server_ts](https://github.com/goto-eof/oh_telemetry_collector_server_ts)

(Remember first to run all three docker containers: docker-compose up)

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

#### Run artillery for typescript API and generate report

```bash
npm run typescript
```

#### Run artillery (sequentially) for all of them and generate reports

```bash
npm run java && npm run rust && npm run typescript
```

or 

```bash
npm run all
```