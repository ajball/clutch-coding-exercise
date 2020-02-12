# Clutch Scala Stock Watcher

A Scala/Play2 backend that exposes a web-service & websocket API for stock searching, and adding & removing stocks to/from a real-time stock price watcher

## Prerequisites & Assumptions

- You are working on MacOS
- You have [homebrew](https://brew.sh/) installed
- You have the [Java 8](https://adoptopenjdk.net/) jdk and runtime installed (`brew cask install adoptopenjdk8`)
	- My output from `java -version`: `openjdk version "1.8.0_222"`
- You have scala installed (`brew install sbt`)
	- `sbt sbtVersion` ==> `1.3.8`

###Steps to boot it up

1. Clone this repo locally
	- `git clone https://github.com/ajball/clutch-coding-exercise.git`
2. Navigate to the project root dir
	-  `cd clutch-scala-exercise`
3. Start the app
	- `sbt run`
	- Alternatively, you can open the project in Intellij and create a Scala Play2 run configuration to boot up the server. Found this to be more reliable at times, especially when I ran into problems related to stale or missing dependencies
4. Open Postman or Google Chrome and request `http://localhost:9000`. Might take several seconds for the class files to compile and whatnot, but if the app started successfully, you should you should see the following json response:

```
{
  "search_stocks_url": "GET /stocks?search=${searchTerm}",
  "init_stock_watcher_url": "GET /watch",
  "add_stock_to_watcher_url": "POST /stocks Body: { symbol: ${symbol} }",
  "remove_stock_from_watcher_url": "DELETE /stocks/${symbol}"
}
```

### Front-End dependencies

There's a javascript client that was built to consume the stock watcher backend. You can find it [here](https://github.com/ajball/clutch-coding-exercise-client) with instructions on how to get it up and running also
