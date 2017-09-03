---
layout: default
---


# Getting started with Scala, Spark and Intellij IDEA

1. In IntelliJ Idea do File -> New -> Project -> Scala -> SBT -> (select location and name for project) -> Finish.

2. Look for build.sbt in the directory structure on the left and edit so that it reads:

	````
	scalaVersion := "2.11.7"

	libraryDependencies += "org.apache.spark" % "spark-core_2.11" % "2.2.0"
	libraryDependencies += "com.github.fommil.netlib" % "all" % "1.1.2"
	libraryDependencies += "org.apache.spark" %% "spark-mllib" % "2.2.0"

	````
Note: Mllib does not currently work with later versions of scala

3. **Bring in the dependencies**

Open up Termninal in the same folder as your main project folder and run 

```
sbt update
```

or go to view>Toolbars>Terminal and do it there, or do view>Tool windows>SBT projects and the press refresh button

4. Go to src/main/scala, right click, new>scala class, WordCount.scala and choose object from the drop-down instead of class

5. Type in the following:

	````
	package org.apache.spark.examples.ml

// $example on$
import org.apache.spark.ml.regression.LinearRegression
// $example off$
import org.apache.spark.sql.SparkSession

object LinearRegressionWithElasticNetExample {

  def main(args: Array[String]): Unit = {
    val spark = SparkSession
      .builder
      .appName("LinearRegressionWithElasticNetExample")
      .config("spark.master", "local")
      .getOrCreate()

    // $example on$
    // Load training data
    val training = spark.read.format("libsvm")
      .load("data/mllib/sample_linear_regression_data.txt")

    val lr = new LinearRegression()
      .setMaxIter(10)
      .setRegParam(0.3)
      .setElasticNetParam(0.8)

    // Fit the model
    val lrModel = lr.fit(training)

    // Print the coefficients and intercept for linear regression
    println(s"Coefficients: ${lrModel.coefficients} Intercept: ${lrModel.intercept}")

    // Summarize the model over the training set and print out some metrics
    val trainingSummary = lrModel.summary
    println(s"numIterations: ${trainingSummary.totalIterations}")
    println(s"objectiveHistory: [${trainingSummary.objectiveHistory.mkString(",")}]")
    trainingSummary.residuals.show()
    println(s"RMSE: ${trainingSummary.rootMeanSquaredError}")
    println(s"r2: ${trainingSummary.r2}")
    // $example off$

    spark.stop()
  }
}

	````

6. Download this[https://github.com/apache/spark/blob/master/data/mllib/sample_linear_regression_data.txt] and put it into file as data/ (not src/main/)

7. Run your code: Ctrl+Shift+F10 or sbt run

8. Your console output should end with this (exact numbers may vary):

	````
	| -2.2653482182417406|
	|-0.10308920436195645|
	|  -1.380034070385301|
	+--------------------+
	only showing top 20 rows

	RMSE: 10.189077167598475
	r2: 0.022861466913958184
	17/09/03 16:16:05 INFO SparkUI: Stopped Spark web UI at http://10.0.2.15:4040
	17/09/03 16:16:05 INFO MapOutputTrackerMasterEndpoint: MapOutputTrackerMasterEndpoint stopped!
	17/09/03 16:16:05 INFO MemoryStore: MemoryStore cleared
	17/09/03 16:16:05 INFO BlockManager: BlockManager stopped
	17/09/03 16:16:05 INFO BlockManagerMaster: BlockManagerMaster stopped
	17/09/03 16:16:05 INFO OutputCommitCoordinator$OutputCommitCoordinatorEndpoint: OutputCommitCoordinator stopped!
	17/09/03 16:16:05 INFO SparkContext: Successfully stopped SparkContext
	17/09/03 16:16:05 INFO ShutdownHookManager: Shutdown hook called
	17/09/03 16:16:05 INFO ShutdownHookManager: Deleting directory /tmp/spark-2b8454f2-bce4-4aaa-815f-9fafe534b042

	````



