# 1.-
`docker cp ./MapReduceSudoku/hadoop-examples-0.20.205.0.jar namenode:/tmp`


# 2.-
`docker cp ./MapReduceSudoku/puzzle1.dta namenode:/tmp `

# 3.-
`cd tmp`
`hadoop jar hadoop-examples-0.20.205.0.jar sudoku puzzle1.dta`

# 4.- 
`hadoop jar hadoop-examples-0.20.205.0.jar sudoku puzzle1.dta > solucion_puzzle1.dta`

# Docs
https://hadoop.apache.org/docs/stable/api/org/apache/hadoop/examples/dancing/package-summary.html