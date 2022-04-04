# Lexical-Scoping
## source("~/lexicalScoping.R")
## I set the input x as a matrix
## set solved value "s" as a null

## I changed to each and every "mean" to solve

makeCacheMatrix <- function(x = matrix ()) {
  s <- NULL
  set <- function(y) {
    x <<- y
    s <<- NULL
  }
  get <- function() x
  setsolve <- function(solve) s <<- solve
  getsolve <- function() s
  
  list(set=set, get=get,
       setsolve = setsolve,
       getsolve = getsolve)
}

##
## same as here "mean" changed to "solve" and "m" to "s"
## return changed to "retval"

cacheSolve <- function(x, ...) {
  s <- x$getsolve()
  if(!is.null(s)) {
    message("get inversed matrix")
    retval(s)
    
  }
  
data <- x$get()
s <- solve(data, ...)
x$setsolve (s)
s
}


## m <- makeCachematrix(matrix(1:4,2,2)
## m$get()
## m$getsolve()
## cacheSolve(m)
#### cacheSolve(m)
