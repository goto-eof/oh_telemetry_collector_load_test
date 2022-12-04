### Run artillery and make report

OH telemetry collector load test was developed for testing the application workload in order to allow to make a comparison between the POC in Java and the one in rust.

The applciations for load test comparison are the following:

- [oh_telemetry_collector_server_rust](https://github.com/goto-eof/oh_telemetry_collector_server_rust)
- [oh_telemetry_collector_server_java](https://github.com/goto-eof/oh_telemetry_collector_server_java)

#### Install packages

```bash
npm install
```

#### Run artillery for rust API

```bash
artillery run  --output report_rust.json  load_test_rust.yml && artillery report --output report_rust.html report_rust.json
```

#### Run artillery for java API

```bash
artillery run  --output report_java.json  load_test_java.yml && artillery report --output report_java.html report_java.json
```

#### Run artillery for both, rust and java projects

```bash
artillery run  --output report_rust.json  load_test_rust.yml && artillery report --output report_rust.html report_rust.json && artillery run  --output report_java.json  load_test_java.yml && artillery report --output report_java.html report_java.json
```