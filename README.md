# EUREKA SERVER

### Start multiple eureka server nodes on local machine:

* Start first node
```bash
./gradlew bootRun
```

* Start second node
```bash
./gradlew bootRun -Peureka-2
```

### Web dashboard will be available on:

* [first node url](http://localhost:8761)
* [second node url](http://localhost:8762)

### Get information of registered service:

```bash
curl http://localhost:8761/eureka/apps/<SERVICE-ID> -H "Accept: application/json" | jq
```

* Response example:
```code
{
  "application": {
    "name": "EUREKA-SERVER-1",
    "instance": [
      {
        "instanceId": "unix:eureka-server-1:8761",
        "hostName": "localhost",
        "app": "EUREKA-SERVER-1",
        "ipAddr": "192.168.0.20",
        "status": "UP",
        "overriddenStatus": "UNKNOWN",
        "port": {
          "$": 8761,
          "@enabled": "true"
        },
        "securePort": {
          "$": 443,
          "@enabled": "false"
        },
        "countryId": 1,
        "dataCenterInfo": {
          "@class": "com.netflix.appinfo.InstanceInfo$DefaultDataCenterInfo",
          "name": "MyOwn"
        },
        "leaseInfo": {
          "renewalIntervalInSecs": 30,
          "durationInSecs": 90,
          "registrationTimestamp": 1555765090563,
          "lastRenewalTimestamp": 1555768211273,
          "evictionTimestamp": 0,
          "serviceUpTimestamp": 1555765030685
        },
        "metadata": {
          "management.port": "8761"
        },
        "homePageUrl": "http://localhost:8761/",
        "statusPageUrl": "http://localhost:8761/actuator/info",
        "healthCheckUrl": "http://localhost:8761/actuator/health",
        "vipAddress": "eureka-server-1",
        "secureVipAddress": "eureka-server-1",
        "isCoordinatingDiscoveryServer": "true",
        "lastUpdatedTimestamp": "1555765090563",
        "lastDirtyTimestamp": "1555765030337",
        "actionType": "ADDED"
      }
    ]
  }
}
```