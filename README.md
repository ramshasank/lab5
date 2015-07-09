scala> var input=sc.textFile("example.txt")
scala> var w=input.flatMap(l=>l.split(" ")).map(word=>(word,1)).cache()
scala> w.reduceByKey(_+_)
scala> counts.collect()
scala> val freq= counts.reduceByKey(_+_)
scala> val top= freq.map(_.swap).top(10)


