# stairway-to-scala

## First Steps in Scala

### Scala Interpreter (REPL)

```
$ scala
```

``` 
scala> 1 + 1
res0: Int = 2
```

``` 
scala> 1 * 4
res1: Int = 4
```

``` 
scala> res0 * 2
res2: Int = 4
```

``` 
scala> 2.0 * 3.0
res3: Double = 6.0
```


### Hello, World!

``` 
scala> println("hello, world")
hello, world
```

### Defining Variables

```
scala> val msg = "hello, world"
msg: String = hello, world
```

```
scala> val msg: java.lang.String = "hello, world"
msg: java.lang.String = hello, world
```

```
scala> val msg: String = "hello, world"
msg: String = hello, world
```

```
scala> res0 + res1
msg: Int = 6
```

```
scala> val msg = res0 + res1
msg: Int = 6
```

### Vals and Vars

```
scala> val msg: String = "hello, world"
msg: String = hello, world
```

```
scala> println(msg)
hello, world
```

```
scala> msg = "something else"
<console>:8: error: reassignment to val
      msg = "something else"
          ^
```

```
scala> var msg: String = "hello, world"
msg: String = hello, world
```

```
scala> var msg: String = "something else"
msg: String = something else
```

```
scala> msg
res7: String = something else
```

### Multi Line Expressions


```
scala> val novel =
     |   "It was the best of times..."
novel: String = It was the best of times...
```

```
scala> val oops
     |   
     |
You typed two blank lines. Starting a new command
```

### Code Completion

```
scala> val s = "howdy"
s: String = howdy
```

```
scala> s.
```
Pressing `Tab` will show 
```
*                     groupBy               scanLeft        
+                     grouped               scanRight       
++                    hasDefiniteSize       segmentLength   
++:                   hashCode              self            
+:                    head                  seq             
/:                    headOption            size            
:+                    indexOf               slice           
:\                    indexOfSlice          sliding         
<                     indexWhere            sortBy          
<=                    indices               sortWith        
>                     init                  sorted          
>=                    inits                 span            
addString             intern                split           
aggregate             intersect             splitAt         
andThen               isDefinedAt           startsWith      
apply                 isEmpty               stringPrefix    
applyOrElse           isTraversableAgain    stripLineEnd    
canEqual              iterator              stripMargin     
capitalize            last                  stripPrefix     
charAt                lastIndexOf           stripSuffix     
chars                 lastIndexOfSlice      subSequence     
codePointAt           lastIndexWhere        substring       
codePointBefore       lastOption            sum             
codePointCount        length                tail            
codePoints            lengthCompare         tails           
collect               lift                  take            
collectFirst          lines                 takeRight       
combinations          linesIterator         takeWhile       
companion             linesWithSeparators   to              
compare               map                   toArray         
compareTo             matches               toBoolean       
compareToIgnoreCase   max                   toBuffer        
compose               maxBy                 toByte          
concat                min                   toCharArray     
contains              minBy                 toDouble        
containsSlice         mkString              toFloat         
contentEquals         nonEmpty              toIndexedSeq    
copyToArray           offsetByCodePoints    toInt           
copyToBuffer          orElse                toIterable      
corresponds           padTo                 toIterator      
count                 par                   toList          
diff                  partition             toLong          
distinct              patch                 toLowerCase     
drop                  permutations          toMap           
dropRight             prefixLength          toSeq           
dropWhile             product               toSet           
endsWith              r                     toShort         
equals                reduce                toStream        
equalsIgnoreCase      reduceLeft            toString        
exists                reduceLeftOption      toTraversable   
filter                reduceOption          toUpperCase     
filterNot             reduceRight           toVector        
find                  reduceRightOption     transpose       
flatMap               regionMatches         trim            
flatten               replace               union           
fold                  replaceAll            unzip           
foldLeft              replaceAllLiterally   unzip3          
foldRight             replaceFirst          updated         
forall                repr                  view            
foreach               reverse               withFilter      
format                reverseIterator       zip             
formatLocal           reverseMap            zipAll          
genericBuilder        runWith               zipWithIndex    
getBytes              sameElements                          
getChars              scan
```

### Shell: Commands

```
scala> :help
```
will show 
```
All commands can be abbreviated, e.g., :he instead of :help.
:completions <string>    output completions for the given string
:edit <id>|<line>        edit history
:help [command]          print this summary or command-specific help
:history [num]           show the history (optional num is commands to show)
:h? <string>             search the history
:imports [name name ...] show import history, identifying sources of names
:implicits [-v]          show the implicits in scope
:javap <path|class>      disassemble a file or class name
:line <id>|<line>        place line(s) at the end of history
:load <path>             interpret lines in a file
:paste [-raw] [path]     enter paste mode or paste a file
:power                   enable power user mode
:quit                    exit the interpreter
:replay [options]        reset the repl and replay all previous commands
:require <path>          add a jar to the classpath
:reset [options]         reset the repl to its initial state, forgetting all session entries
:save <path>             save replayable session to a file
:sh <command line>       run a shell command (result is implicitly => List[String])
:settings <options>      update compiler options, if possible; see reset
:silent                  disable/enable automatic printing of results
:type [-v] <expr>        display the type of an expression without evaluating it
:kind [-v] <type>        display the kind of a type. see also :help kind
:warnings                show the suppressed warnings from the most recent line which had any
```

hello.scala
```scala
println("Hello, world")
```

```
scala> :load hello.scala
Loading hello.scala...
Hello, world
```

```
scala> :history
```

```
scala> :replay
```

```
scala> :sh ls
res2: scala.tools.nsc.interpreter.ProcessResult = `ls` (4 lines, exit 0)
```

```
scala> res2.lines
res3: List[String] = List(build.sbt, project, src, target)
```

### Java's If Statement and Scala's If Expression!

```
scala> val a = 1
a: Int = 1
```

```
scala> val b = 2
b: Int = 2
```

```
scala> if (a > b)
     |   System.out.println(a);
```

```
scala> :paste
// Entering paste mode (ctrl-D to finish)

if (a > b)
  System.out.println(a);
else
  System.out.println(b);
  
// Exiting paste mode, now interpreting.

2
```

```
scala> val m = if (a > b) a else b
m: Int = 2
```

```
scala> println(m)
2
```

### Defining a Function

```
scala> def max(x: Int, y: Int): Int = {
     |   if (x > y) x else y
     | }
max: (x: Int, y: Int)Int
```

```
scala> max(3, 4)
res3: Int = 4
```

```
scala> max(4, 3)
res4: Int = 4
```

### Streamlining a Function

```
scala> def max(x: Int, y: Int) = {
     |   if (x > y) x else y
     | }
max: (x: Int, y: Int)Int
```

```
scala> def max(x: Int, y: Int) = if (x > y) x else y
max: (x: Int, y: Int)Int
```

```
scala> def greet() = println("hello, world")
greet: ()Unit
```

```
scala> greet() 
hello, world
```

```
scala> def greet(): Unit = println("hello, world")
greet: ()Unit
```

### Scala Scripting

helloarg.scala
```scala
println("Hello, " + args(0) + "!")
```

```
$ scala helloarg.scala planet
Hello planet!
```

helloarg.scala
```scala
println(s"Hello, ${args(0)}!")
```

### While Loop

whileLoop.scala
```scala
var i = 0
while (i < args.length) {
  println(args(i))
  i += 1
}
```

```
$ scala whileLoop.scala Scala is fun
Scala 
is 
fun
```

### "Looping" with a for expression:

forLoop.scala
```scala
for (arg <- args)
  println(arg)
```

```
$ scala forLoop.scala Scala is fun
Scala 
is 
fun
```

### Looping with foreach

foreach.scala
```scala
args.foreach((arg: String) => println(arg))
```

foreach.scala
```scala
args.foreach(arg => println(arg))
```

foreach.scala
```scala
args.foreach(println)
```

foreach.scala
```scala
// Operation notation, change ".", "(", ")" for spaces
args foreach println
```

```
$ scala foreach.scala Scala is fun
Scala 
is 
fun
```

### Function Literal Syntax

```
scala> def max(x: Int, y: Int) = if (x > y) x else y
max: (x: Int, y: Int)Int
```

```
scala> max(3, 6)
res0: Int = 6
```

```
scala> (x: Int, y: Int) => if (x > y) x else y
res1: (Int, Int) => Int = <function2>
```
