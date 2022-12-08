### OH Telemetry Collector loan test

OH telemetry collector loan test was developed for testing the applications workload. So that we can make a comparison between the POC in Java, Rust and TypeScript.

The applications are the following:

- [oh_telemetry_collector_server_rust](https://github.com/goto-eof/oh_telemetry_collector_server_rust) (Rust, Warp, Sea-ORM, Postgres)
- [oh_telemetry_collector_server_java](https://github.com/goto-eof/oh_telemetry_collector_server_java) (Java, Spring Boot, Hibernate, Postgres)
- [oh_telemetry_collector_server_ts](https://github.com/goto-eof/oh_telemetry_collector_server_ts) (Typescript, Express, TypeORM, Postgres)

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
npm run js
```

#### Run artillery (sequentially) for all of them and generate reports

```bash
npm run java && npm run rust && npm run js
```

or 

```bash
npm run all
```

### Moreover

Java server responds on: `http://127.0.0.1:8013`
Rust server responds on: `http://127.0.0.1:8017`
JS server responds on: `http://127.0.0.1:8019`


P.S. If you have a mac and the java loan test does not work, it could be that the Dockers VM has not enought space for the application container, so that change settings of VM. 
