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


## Next Steps in Scala

### Flight 02 Goals

- Get familiar with collections
- Look at what it means to be "functional"
- Learn how to process files with Scala scripts

### Parameterize Arrays with Types

```
scala> val greetStrings = new Array[String](3)
greetStrings: Array[String] = Array(null, null, null)
```

```
scala> greetStrings(0) = "Hello"
```

```
scala> greetStrings(1) = ", "
```

```
scala> greetStrings(2) = "world!\n"
```

```
scala> for (i <- 0 to 2)
     |   print(greetStrings(i))
Hello, world!
```

### All Operations are Methods Calls

```
scala> 3.0 + 4.0
res4: Double = 7.0
```

```
scala> 3.0.+(4.0)
res5: Double = 7.0
```

```
scala> "hello".charAt(2)
res6: Char = l
```

```
scala> "hello".charAt(1)
res7: Char = e
```

Infix Notation, if you've got a single item method call:
```
scala> "hello" charAt 1
res8: Char = e
```

When people say that Scala has operator overloading that's not really true.
What it has is symbolic operator names, in other words you can call your methods plus, minus, star or star plus star or other way of combinations whatever you want to think of

### apply and update

```
scala> greetStrings(1)
res9: String = ", "
```

```
scala> greetStrings.apply(1)
res10: String = ", "
```

```
scala> greetStrings(1) = ", "
```

```
scala> greetStrings.update(1, " crazy ")
```

```
scala> greetStrings
res13: Array[String] =
Array(Hello, " crazy ", "world!
")
```


### Creating and Initializing an Array

```
scala> val numNames = Array("zero", "one", "two")
numNames: Array[String] = Array(zero, one, two)
```

```
scala> val numNames = Array.apply("zero", "one", "two")
numNames: Array[String] = Array(zero, one, two)
```

```
scala> val numNames: Array[String] = Array.apply("zero", "one", "two")
numNames: Array[String] = Array(zero, one, two)
```

```
scala> val numNames: Array[Int] = Array.apply("zero", "one", "two")
<console>:11: error: type mismatch;
 found   : String("zero")
 required: Int
       val numNames: Array[Int] = Array.apply("zero", "one", "two")
                                              ^
<console>:11: error: type mismatch;
 found   : String("one")
 required: Int
       val numNames: Array[Int] = Array.apply("zero", "one", "two")
                                                      ^
<console>:11: error: type mismatch;
 found   : String("two")
 required: Int
       val numNames: Array[Int] = Array.apply("zero", "one", "two")
                                                             ^
```

```
scala> List(1,2,3)
res14: List[Int] = List(1,2,3)
```

```
scala> List.apply(1,2,3)
res15: List[Int] = List(1,2,3)
```


### Creating and Initializing a List

```
scala> val oneTwoThree = List.apply(1,2,3)
oneTwoThree: List[Int] = List(1, 2, 3)
```

### Lists are Immutable

```
scala> val oneTwo = List(1,2)
oneTwo: List[Int] = List(1, 2)
```

```
scala> val threeFour = List(3,4)
threeFour: List[Int] = List(3, 4)
```

```
scala> oneTwo ::: threeFour
res16: List[Int] = List(1, 2, 3, 4)
```

```
scala> oneTwoThreeFour = oneTwo ::: threeFour
oneTwoThreeFour: List[Int] = List(1, 2, 3, 4)
```

```
scala> oneTwo 
res17: List[Int] = List(1, 2)
```

```
scala> threeFour 
res18: List[Int] = List(3, 4)
```

### Consing Lists

```
scala> val twoThree = List(2,3) 
twoThree: List[Int] = List(2, 3)
```

```
scala> 1 :: twoThree 
res19: List[Int] = List(1, 2, 3)
```

```
scala> (1).::(twoThree) 
<console>:13: error: value :: is not a member of Int
       (1).::(twoThree)
           ^
```

```
scala> (twoThree).::(1)
res21: List[Int] = List(1, 2, 3)
```

### Initializing Lists with Cons and Nil

```
scala> val nums = List(1,2,3)
nums: List[Int] = List(1, 2, 3)
```

```
scala> val nums = 1 :: 2 :: 3 :: Nil
nums: List[Int] = List(1, 2, 3)
```

### Converting between Lists and Arrays

```
scala> twoThree
res22: List[Int] = List(2, 3)
```

```
scala> val oneTwoThree = 1 :: twoThree
oneTwoThree: List[Int] = List(1, 2, 3)
```

```
scala> val zeroTwoThree = 0 :: twoThree
zeroTwoThree: List[Int] = List(0, 2, 3)
```


```
scala> val anotherOneTwoThree = 1 :: twoThree
anotherOneTwoThree: List[Int] = List(1, 2, 3)
```

```
scala> oneTwoThree == anotherOneTwoThree
res23: Boolean = true
```

```
scala> oneTwoThree eq anotherOneTwoThree
res24: Boolean = false
```

```
scala> oneTwoThree == zeroTwoThree
res25: Boolean = false
```

```
scala> oneTwoThree.tail == zeroTwoThree.tail
res26: Boolean = true
```

```
scala> oneTwoThree.tail 
res27: List[Int] = List(2, 3)
```

```
scala> oneTwoThree.tail eq zeroTwoThree.tail
res28: Boolean = true
```

```
scala> Nil
res29: scala.collection.immutable.Nil.type = List()
```

```
scala> Array(1,2,3).toList
res30: List[Int] = List(1, 2, 3)
```

```
scala> List('a', 'b', 'c').toArray
res31: Array[Char] = Array(a, b, c)
```

```
scala> Array(1,2,3).toArray
res32: Array[Int] = Array(1, 2, 3)
```

```
scala> List(1,2,3).toList
res33: List[Int] = List(1, 2, 3)
```

```
scala> List(1,2,3).toVector
res34: Vector[Int] = Vector(1, 2, 3)
```

```
scala> List(1,2,3).to[Vector]
res35: Vector[Int] = Vector(1, 2, 3)
```

### Creating and Using a Tuple

```
scala> 1 :: Nil
res36: List[Int] = List(1)
```

```
scala> true :: 1 :: Nil
res37: List[AnyVal] = List(true, 1)
```

```
scala> "string" :: true :: 1 :: Nil
res38: List[Any] = List(string, true, 1)
```

```
scala> ("hello", true, 1)
res39: (String, Boolean, Int) = (hello,true,1)
```

```
scala> val myTup = ("hello", true, 1)
myTup: (String, Boolean, Int) = (hello,true,1)
```

```
scala> myTup._1
res40: String = hello
```

```
scala> myTup._2
res41: Boolean = true
```

```
scala> if (myTup._2) println("It's true")
It's true
```

```
scala> if (myTup._1) println("It's true")
<console>:13: error: type mismatch;
 found   : String
 required: Boolean
       if (myTup._1) println("It's true")
                 ^
```

```
scala> myTup._3
res44: Int = 1
```

```
scala> myTup._4
<console>:13: error: value _4 is not a member of (String, Boolean, Int)
       myTup._4
             ^
```

```
scala> val (a,b,c) = myTup
a: String = hello
b: Boolean = true
c: Int = 1
```

```
scala> val (a,b,_) = myTup
a: String = hello
b: Boolean = true
```

### Tuple Types

```
scala> val tup6: Tuple6[Char, Char, String, Int, Int, String] = ('u', 'r', "the",1,4,"me")
tup6: (Char, Char, String, Int, Int, String) = (u,r,the,1,4,me)
```

```
scala> val tup6: Tuple6[Char, Char, String, String, Int, String] = ('u', 'r', "the",1,4,"me")
<console>:11: error: type mismatch;
 found   : Int(1)
 required: String
       val tup6: Tuple6[Char, Char, String, String, Int, String] = ('u', 'r', "the",1,4,"me")
                                                                                    ^
```

### Set Hierarchy

![alt text](https://lh5.googleusercontent.com/WhGZMb4mL-gxPiNHPv1FkrB5Duimr08xuJTByaN5V4Yzs29IN_ug0v0GMBk2RXtm9e16yZvG7EVIYA=w937-h970)

```
scala> Set(1,2,3)
res47: scala.collection.immutable.Set[Int] = Set(1, 2, 3)
```

```
scala> import scala.collection.mutable
import scala.collection.mutable
```

```
scala> import scala.collection.mutable
import scala.collection.mutable
```

```
scala> mutable.Set(1,2,3)
res48: scala.collection.mutable.Set[Int] = Set(1, 2, 3)
```

```
scala> scala.collection.Set
res49: collection.Set.type = scala.collection.Set$@2323368c
```

```
scala> val x1: scala.collection.Set[Int] = Set(1,2,3)
x1: scala.collection.Set[Int] = Set(1, 2, 3)
```

```
scala> val x1: scala.collection.Set[Int] = mutable.Set(1,2,3)
x1: scala.collection.Set[Int] = Set(1, 2, 3)
```

### Creating, Initializing and Using an Immutable Set

```
scala> var jetSet = Set("Boeing", "Airbus")
jetSet: scala.collection.immutable.Set[String] = Set(Boeing, Airbus)
```

```
scala> jetSet += "Lear"
```

```
scala> jetSet
res51: scala.collection.immutable.Set[String] = Set(Boeing, Airbus, Lear)
```

```
scala> jetSet.+=("Lear")
```

```
scala> jetSet
res53: scala.collection.immutable.Set[String] = Set(Boeing, Airbus, Lear)
```

```
scala> jetSet.+=("Cessna")
```

```
scala> jetSet
res55: scala.collection.immutable.Set[String] = Set(Boeing, Airbus, Lear, Cessna)
```

```
scala> jetSet.
&              exists               min                 tails           
&~             filter               minBy               take            
+              filterNot            mkString            takeRight       
++             find                 nonEmpty            takeWhile       
++:            flatMap              par                 to              
-              flatten              partition           toArray         
--             fold                 product             toBuffer        
/:             foldLeft             reduce              toIndexedSeq    
:\             foldRight            reduceLeft          toIterable      
WithFilter     forall               reduceLeftOption    toIterator      
addString      foreach              reduceOption        toList          
aggregate      genericBuilder       reduceRight         toMap           
andThen        groupBy              reduceRightOption   toSeq           
apply          grouped              repr                toSet           
canEqual       hasDefiniteSize      sameElements        toStream        
collect        hashCode             scan                toString        
collectFirst   head                 scanLeft            toTraversable   
companion      headOption           scanRight           toVector        
compose        init                 seq                 transpose       
contains       inits                size                union           
copyToArray    intersect            slice               unzip           
copyToBuffer   isEmpty              sliding             unzip3          
count          isTraversableAgain   span                view            
diff           iterator             splitAt             withFilter      
drop           last                 stringPrefix        zip             
dropRight      lastOption           subsetOf            zipAll          
dropWhile      map                  subsets             zipWithIndex    
empty          max                  sum                 |               
equals         maxBy                tail   
```

Set has no `+=` method
Scala is rewriting it as:

```
scala> jetSet = jetSet + "Saab"
jetSet: scala.collection.immutable.Set[String] = Set(Boeing, Airbus, Lear, Saab, Cessna)
```

### Creating, Initializing and Using an Mutable Set

```
scala> val movieSet = mutable.Set("Hitch", "Poltergeist")
movieSet: scala.collection.mutable.Set[String] = Set(Hitch, Poltergeist)
```

Mutable Sets do have `+=` method

```
scala> movieSet.
&              dropRight            maxBy               sum             
&~             dropWhile            min                 tail            
+              empty                minBy               tails           
++             equals               mkString            take            
++:            exists               nonEmpty            takeRight       
++=            filter               par                 takeWhile       
+=             filterNot            partition           to              
-              find                 product             toArray         
--             flatMap              reduce              toBuffer        
--=            flatten              reduceLeft          toIndexedSeq    
-=             fold                 reduceLeftOption    toIterable      
/:             foldLeft             reduceOption        toIterator      
:\             foldRight            reduceRight         toList          
<<             forall               reduceRightOption   toMap           
WithFilter     foreach              remove              toSeq           
add            genericBuilder       repr                toSet           
addString      groupBy              result              toStream        
aggregate      grouped              retain              toString        
andThen        hasDefiniteSize      sameElements        toTraversable   
apply          hashCode             scan                toVector        
canEqual       head                 scanLeft            transpose       
clear          headOption           scanRight           union           
clone          init                 seq                 unzip           
collect        inits                size                unzip3          
collectFirst   intersect            sizeHint            update          
companion      isEmpty              sizeHintBounded     view            
compose        isTraversableAgain   slice               withFilter      
contains       iterator             sliding             zip             
copyToArray    last                 span                zipAll          
copyToBuffer   lastOption           splitAt             zipWithIndex    
count          map                  stringPrefix        |               
diff           mapResult            subsetOf                            
drop           max                  subsets  
```

```
scala> movieSet += "Shrek"
res56: movieSet.type = Set(Poltergeist, Shrek, Hitch)
```

### Set Classes other than the default

```
scala> import scala.collection.immutable.HashSet
import scala.collection.immutable.HashSet
```

```
scala> val hashSet = HashSet(1,2,3)
hashSet: scala.collection.immutable.HashSet[Int] = Set(1, 2, 3)
```

### Importing a Package

```
scala> import scala.collection.mutable
import scala.collection.mutable
```

```
scala> Set(1,2,3)
res58: scala.collection.immutable.Set[Int] = Set(1, 2, 3)
```

```
scala> mutable.Set(1,2,3)
res59: scala.collection.mutable.Set[Int] = Set(1, 2, 3)
```

### Map Hierarchy

![alt text](https://lh3.googleusercontent.com/4H5ISf9rf-LXP_hvwLCJ6ZyfokTZIRXkcMi63ZmIUKEy-UpgvSMkzbwd9I-yxq6x0sH9-uX-uRtLXve66OPI=w937-h970)

### Creating, Initializing and Using a Mutable Map

```
scala> val treasureMap = mutable.Map.empty[Int, String]
treasureMap: scala.collection.mutable.Map[Int,String] = Map()
```

```
scala> treasureMap += (1 -> "Go to island.") 
res61: treasureMap.type = Map(1 -> Go to island.)
```

```
scala> treasureMap += (2 -> "Find big X.") 
res62: treasureMap.type = Map(2 -> Find big X., 1 -> Go to island.)
```

```
scala> treasureMap += (3 -> "Dig!") 
res63: treasureMap.type = Map(2 -> Find big X., 1 -> Go to island., 3 -> Dig!)
```

```
scala> println(treasureMap(2))
Find big X.
```

```
scala> println(treasureMap.apply(2))
Find big X.
```

```
scala> treasureMap(2) = "Find the X."
Find the X.
```

```
scala> treasureMap.update(2, "Find the X.")
Find the X.
```

```
scala> treasureMap 
res68: scala.collection.mutable.Map[Int,String] = Map(2 -> Find the X., 1 -> Go to island., 3 -> Dig!)
```

```
scala> 1 -> "Go to island."
res69: (Int, String) = (1,Go to island.)
```

### Implicit Conversions

```
scala> (1).->("Go to island.")
res70: (Int, String) = (1,Go to island.)
```

```
scala> (1).
!=   >             floatValue      isValidInt     to               toRadians    
%    >=            floor           isValidLong    toBinaryString   toShort      
&    >>            getClass        isValidShort   toByte           unary_+      
*    >>>           intValue        isWhole        toChar           unary_-      
+    ^             isInfinite      longValue      toDegrees        unary_~      
-    abs           isInfinity      max            toDouble         underlying   
/    byteValue     isNaN           min            toFloat          until        
<    ceil          isNegInfinity   round          toHexString      |            
<<   compare       isPosInfinity   self           toInt                         
<=   compareTo     isValidByte     shortValue     toLong                        
==   doubleValue   isValidChar     signum         toOctalString 
```

```
scala> ArrowAssoc(1)
res7: ArrowAssoc[Int] = scala.Predef$ArrowAssoc@1
```

```
scala> ArrowAssoc(1).
->   equals   getClass   hashCode   →
```

```
scala> ArrowAssoc(1).->("yo")
res72: (Int, String) = (1,yo)
```

```
scala> "hello".reverse
res73: String = olleh
```

```
scala> 1 -> "yo"
res74: (Int, String) = (1,yo)
```

```
scala> "yo" -> 1
res75: (Int, String) = (yo,1)
```

### Creating, Initializing and Using a Immutable Map

```
scala> val romanNumeral = Map(1 -> "I", 2 -> "II", 3 -> "III", 4 -> "IV", 5 -> "V")
romanNumeral: scala.collection.immutable.Map[Int,String] = Map(5 -> V, 1 -> I, 2 -> II, 3 -> III, 4 -> IV)
```

```
scala> val rn2 = Map((1, "I"), (2, "II"))
rn2: scala.collection.immutable.Map[Int,String] = Map(1 -> I, 2 -> II)
```

### An Imperative Method

Imperative vs Fuctional

```
scala> def printArgs(agrs: Array[String]): Unit = {
     |   var i = 0
     |   while (i < args.length) {
     |     prinln(args(i))
     |     i += 1
     |   }
     | }
printArgs: (args: Array[String])Unit
```

```
scala> printArgs(Array("hello", "there"))
hello
there
```

### A More Functional Method

```
scala> def printArgs(args: Array[String]): Unit = {
     |   for (arg <- args) println(arg)
     | }
printArgs: (args: Array[String])Unit
```

```
scala> printArgs(Array("hello", "there"))
hello
there
```

```
scala> val args = Array("hello", "world")
args: Array[String] = Array(hello, world)
```

```
scala> for (arg <- args) println(args)
hello
world
```

```
scala> args.foreach(arg => println(arg))
hello
world
```

### A Fully Functional Method

```
scala> args.foreach(println)
hello
world
```

```
scala> def formatArgs(args: Array[String]): String = args.mkString("\n")
formatArgs: (args: Array[String])String
```

```
scala> formatArgs(args)
res81: String =
hello
world
```

```
scala> res81
res82: String =
hello
world
```

```
scala> res81 == "hello\nworld"
res83: Boolean = true
```

### Balanced Attitude

Prefer vals, immutable objects and methods without side effects. 
Reach for them first.
Use vars, mutable objects, and methods with side effects when you have a specific need and justification for them.

### Reading Lines from a File

```
$ mkdir ScalaDemo
$ cd ScalaDemo
$ nano readlines.scala
```

readlines.scala
```
import scala.io.Source

if (args.length > 0) {
  for (line <- Source.fromFile(args(0)).getLines) 
    println(line.length + ": " + line)
}
else Console.err.println("Please enter a filename")
```

### Running the Example

```
$ scala readlines.scala readlines.scala
22: import scala.io.Source
0: 
22: if (args.length > 0) {
50:   for (line <- Source.fromFile(args(0)).getLines) 
38:     println(line.length + ": " + line)
1: }
51: else Console.err.println("Please enter a filename")
```
