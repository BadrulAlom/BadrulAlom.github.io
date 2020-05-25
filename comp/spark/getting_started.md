---
layout: default
---


# Getting started with Scala, Spark and Intellij IDEA

1. In IntelliJ Idea go to File -> New -> Project -> Scala -> SBT -> (select location and name for project) -> Finish.

2. Look for build.sbt in the directory structure on the left and edit so that it reads:

	````
	name := "WordCount"

	version := "0.1"

	scalaVersion := "2.11.3"
	libraryDependencies += "org.apache.spark" % "spark-core_2.11" % "2.2.0"
	````

3. **Bring in the dependencies**

Open up Terminal in the same folder as your main project folder and run 

```
sbt update
```

or go to view>Toolbars>Terminal and do it there, or do view>Tool windows>SBT projects and the press refresh button

4. Go to src/main/scala, right click, new>scala class, WordCount.scala and choose object from the drop-down instead of class

5. Type in the following:

	````
	import org.apache.spark.{SparkConf, SparkContext}

	object WordCount {
	  def main(args: Array[String]) {
	    val conf = new SparkConf()
	      .setMaster("local")
	      .setAppName("Word Count")
	      .setSparkHome("src/main/resources")
	    val sc = new SparkContext(conf)
	    val input = sc.textFile("src/main/resources/input.txt")
	    val count = input.flatMap(line ⇒ line.split(" "))
	      .map(word ⇒ (word, 1))
	      .reduceByKey(_ + _)
	    count.saveAsTextFile("src/main/resources/outfile")
	    println("OK")
	  }
	}

	````

6. Put input.txt into file as src/main/resources/

7. Run your code: Ctrl+Shift+F10 or sbt run

8. Your console output should end with this:

	````
	7/09/02 14:57:13 INFO DAGScheduler: ResultStage 1 (saveAsTextFile at WordCount.scala:20) finished in 0,223 s
	17/09/02 14:57:13 INFO DAGScheduler: Job 0 finished: saveAsTextFile at WordCount.scala:20, took 1,222133 s
	OK
	17/09/02 14:57:13 INFO SparkContext: Invoking stop() from shutdown hook
	17/09/02 14:57:13 INFO SparkUI: Stopped Spark web UI at http://192.168.1.104:4040
	17/09/02 14:57:13 INFO MapOutputTrackerMasterEndpoint: MapOutputTrackerMasterEndpoint stopped!
	17/09/02 14:57:13 INFO MemoryStore: MemoryStore cleared
	17/09/02 14:57:13 INFO BlockManager: BlockManager stopped
	17/09/02 14:57:13 INFO BlockManagerMaster: BlockManagerMaster stopped
	17/09/02 14:57:13 INFO OutputCommitCoordinator$OutputCommitCoordinatorEndpoint: OutputCommitCoordinator stopped!
	17/09/02 14:57:13 INFO SparkContext: Successfully stopped SparkContext
	17/09/02 14:57:13 INFO ShutdownHookManager: Shutdown hook called
	17/09/02 14:57:13 INFO ShutdownHookManager: Deleting directory /tmp/spark-663047b2-415a-45b5-bcad-20bd18270baa

	Process finished with exit code 0
	````
9. In folder src/main/resources there should appear new subfolder outfile with several files.


