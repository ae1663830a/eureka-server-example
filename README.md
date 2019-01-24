EUREKA SERVER

to start multiple eureka server nodes on local machine:

* Start first node
```bash
./gradlew bootRun
```

* Start second node
```bash
./gradlew bootRun -Peureka-2
```

Web dashboard will be available on:

* [first node url](http://localhost:8761)
* [second node url](http://localhost:8762)