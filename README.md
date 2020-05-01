Data Streaming Nanodegree

SF Crime Statistics with Spark Streaming

Q1: How did changing values on the SparkSession property parameters affect the throughput and latency of the data?

By tuning the property parameter 'processedRowsPerSecond', throughput and latency will be changed accordingly. Higer 'processedRowsPerSecond' will result in high throughput and low latency. Vice versa.

Q2: What were the 2-3 most efficient SparkSession property key/value pairs? Through testing multiple variations on values, how can you tell these were the most optimal?

To increase processedRowsPerSecond we can modify following settings:

'spark.default.parallelism': total number of cores on all executor nodes. Optimal can be reached by matching it to be total number of cores among all the machines

'spark.sql.shuffle.partitions': number of partitions to use when shuffling data for joins or aggregations. Optimal can be reached by dividing the overall data size by the size of each partition

'spark.streaming.kafka.maxRatePerPartition': maximum rate at which data will be read from each Kafka partition. Optimal can be reached by dividing the overall message amount by number of partitions and batch duration
