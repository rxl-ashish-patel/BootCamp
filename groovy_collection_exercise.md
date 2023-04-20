## Groovy Collections - Exercise




---




**Question0**  Initialize an empty list and give the output of the following code:

```groovy

l[11] = "myelement"

println l[11]

printin l.get(5)

printin l

```

--- 
**Output** 

> myelement

>null


---


**Question1.**  Initialize a list using a range and find all elements which are even.

**Answer**
>```groovy 
>List l= (1..10).findAll { it%2==0}
>print l 
>```



---




**Question2.**  Create a set from a list containing duplicate elements. What do you observe? How can you achieve the same result without converting a list to a set?

**Answer**
>```groovy 
>def list=[1,2,3,4,3,8,6,9,6,8] 
>println list.unique()
>def set=list as Set
>println set
>```



---




**Question3.**  Given two lists `[11, 12, 13, 14]` and `[13, 14, 15]`, how would we obtain the list of items from the first that are not in the second?

**Answer**
>```groovy
>List l1=[11,12,13,14]
>List l2=[13,14,15] 
>print(l1-l2)
>``` 
**OR**
>```groovy 
>List l1=[11,12,13,14]
>List l2=[13,14,15] 
>println(l1.intersect(l2))
>```     



---




**Question4.**  Find whether two lists have a common element or not

**Answer**
>```groovy 
>List l1=[11,12,13,14]
>List l2=[13,14,15] 
>println(l1.disjoint(l2)) ```




---




**Question5.**  Remove all records from a list whose index is odd.

**Answer**
>```groovy
>List l =[1,2,3,4,5,6,7,8,9]
>int index=0
>l.removeAll( l.findAll{ it -> index++%2==1})
>print l
>```




---




**Question6.**  Consider the following list:

`[1, 2, 3, "element1", 0.3, [2, 4, 6], 0..10]`

Print the class name of each element.




What's the output of the following statement?

list.get(6).get(9) `output is 9`

**Answer**
>```groovy
>List l=[1,2,3,"element1",0.3,[2,4,6],0..10]
>l.each {println it.class}
>println l.get(6).get(9)
>```




---




**Question7.**  Sort the given list in descending order having distinct elements: `[14,12, 11,10, 16, 15, 12, 10, 99, 90, 14, 16, 35]`

**Answer**
>``` groovy 
>List l=[14,12,11,10,16,15,12,10,99,90,14,16,35]
>l.unique().sort({i,j-> j-i})
>println l
>```




---




**Question8.**  Consider a class Employee with following details

* `Name`

* `Age`

* `Salary`  




Create a list consisting of 10 Employee objects.

* (a). Get a list of employees who earn less than 5000

* (b). Get the name of the youngest employee and oldest employee

* (c). Get the employee with maximum salary

* (d). Get the list of names of all the employees

**Answer**
>```groovy 
>class Employee{
>  String Name
>  int Age
>  int Salary 
>  Employee (String Name,int Age,int Salary){
>    this.Name=Name
>    this.Age=Age
>    this.Salary=Salary
>  } 
>  public String toString(){
>    return "{"+Name+" "+Age+" "+Salary+"}"
>  }
>}
>List l=[new Employee("ashish",23,1000),new Employee("amit",13,3000),new Employee("ajay",23,5000),new Employee("ankit",25,7000),new Employee("arjun",24,10000),new Employee("anit",26,4500),new Employee("abhay",24,3700),new Employee("aryn",18,1500),new Employee("ayan",20,15000),new Employee("annu",17,2200)]
>List list1=l.findAll {it.salary<5000}
>println list1 
>int minAge=100 ,maxAge=0,maxSalary=0;
>Employee minAgeEmp=null,maxAgeEmp=null,maxSalaryEmp=null;
>l.each { if(it.Age <= minAge){
>            minAgeEmp=it 
>            minAge=it.Age}
>         if(it.Age>=maxAge){
>            maxAgeEmp=it
>            maxAge=it.Age}
>          if(it.Salary>=maxSalary){
>            maxSalary=it.Salary
>            maxSalaryEmp=it
>          }}
>println(maxAgeEmp)
>println(minAgeEmp)
>println(maxSalaryEmp)
>println(l*.Name)```



---




**Question9.**  Consider the following piece of code:




```groovy

String s = "this string needs to be split"

println s.tokenize(" ")

println s.tokenize()

Compare this with the following code:

String s = "this string needs to be split"

println s.split("")

println s.split(/\s/);

// (Try Same Parameter with tokenize)

Also try the following exercise:

String s = "are.you.trying.to.split.me.mister?" s.tokenize(".")

s.split(".")

```
**Answer**
>`split(".") consider "." as regular expression so it gives empty list while tokenizer(".") consider "." as delimeter`



---




**Question10.**  Get first, second and last element of Range.

**Answer**
>```groovy
>println l[0]
>println l[1]
>println l[-1]
>```



---




**Question11.**  Print the table of a given number: 2 and 12

**Answer**
>```groovy
>(1..10).each {println 2*it}
>(1..10).each {println 10*it}
>```




---




**Question12.**  We have a sorted list of alphabets `a-z`, print all alphabets appearing after `j`

**Answer**
>```groovy
>('a'..'z').each{ if(it >'j') println it}
>```




---




**Question13.**  Find the number of occurences of a character in a string.

**Answer**
>```groovy
>String s="ashish patel"
>int count=0;
>s.each { if(it=='s') count++}
>```


---




**Question14.**  Write a program that prints the numbers from 1 to 100. But for multiples of three print `Fizz` instead of the number and for the multiples of five print `Buzz`. For numbers which are multiples of both three and five print `FizzBuzz`.

**Answer**
>```groovy
>(1..100).each{ if(it%3==0 && it%5==0)
>                  println "FizzBuzz"
>                else if(it%3==0)
>                  println "Fizz"
>                else if(it%5==0)
>                  println "Buzz"
>                else 
>                  println it  }
>
>```




---




**Question15.**  Consider a class named "Stack" that holds a list of objects and has the following operations associated:


* 1) POP - Pops the last element off the stack

* 2) PUSH - Pushes an element on top of the stack

* 3) TOP - Returns the element at the top of the list




Implement the above said class


**Answer**
>```groovy
>class Stack{
>  List l=[]
>  public def POP(){
>    if(l)
>      return l.remove(l[-1])
>    else 
>      {println "empty stack"
>        return -1;
>        }
>  }
>
>  public def PUSH(obj){
>    l.add(obj)
>  }
>  
>  public def TOP(){
>    if(l){
>    return l[-1];
>    }
>    else{
>      println "empty Stack";
>      return -1;
>    }
>  }
>}
>Stack s=new Stack()
>s.POP()
>s.PUSH(1)
>s.PUSH(2)
>println s.TOP()
>```





---




**Question16.**  Create a new map consisting of 10 of your friend's name's as keys and their ages as value.

**Answer**
>```groovy
>Map<String,Integer> map=[:]
>map.put("ashish",23)
>map.put("abhay",22)
>map.put("anit",21)
>map.put("ankit",24)
>map.put("ajay",25)
>map.put("aman",22)
>map.put("anshul",21)
>map.put("arpit",20)
>map.put("amit",19)
>map.put("ashu",25)
>```



---




**Question17.**  Iterate over the previous map in as many ways as possible

**Answer**
>```groovy
>
>map.each {println it.key + " : "+ it.value }
>map.eachWithIndex {it,vindex->
>println it.key + " : " + it.value
> }
>for(entry in map){
>  println entry.key + ":" +entry.value
>}
>map.keySet().each { println it +" : "+ map[it]}
>```




---




**Question18.**  Create a new map by adding two existing maps

**Answer**
>```groovy
>Map<String,Integer> map1=["ashish":23,"abhay":22,"anit":21,"ankit":24]
>Map<String ,Integer>map2=["ajay":25,"aman":22,"anshul":21,"arpit":20,"amit":19,"ashu":25]
>def map3=map1+map2
>```




---




**Question19.**  Try the following code on a map:

```groovy

println map.class

println map.getClass()

```

What do you observe?

**Answer** 
>`null`

>`null`


---




**Question20.**  Consider the following map:

```groovy

Map m = ['1' : 2, '2' : 3, '3' : 4, '2':5]

```

Is this a valid construction? What is the value of m['2']?

**Answer**

>`yes it is valid construction and m['2'] return 5 because at key '2' value has been updated from 3 to 5`




---




**Question21.**  Find if a map contains a particular key.

**Answer**
>```groovy
>println m['5']!=null
>println m.get('5')!=null 
>println m.keySet().contains('5')
>```




---




**Question22.**  Consider the following map:

```groovy

Map m = ['Computing': ['Computing': 600, 'Information Systems' : 300], 'Engineering': ['Civil' : 200, 'Mechanical' : 100], 'Management': ['Management' : 800]]

```

**Answer**


* a) How many university departments are there?

  >`println m.size() `

* b) How many programs are delivered by the Computing department?
  >`println m['Computing'].size()`

* c) How many students are enrolled in the Civil Engineering program?
 
   >`println m['Engineering']['Civil']`




---




**Question23.**  Conside a class named `Employee` which has the following properties:

* 1) Name

* 2) Age

* 3) DepartmentName

* 4) EmployeeNumber

* 5) Salary

Let's say that there's a list of 50 employees available.  




Perform the following operations on the list of employees:  

* a) Group the employees on the basis of the bracket in which their salary falls. The ranges are 0-5000, 5001 and 10000, and so on.

>```groovy
>println list.groupBy { if(it.salary==0)
>                  return 1 
>                else
>                  return (int)Math.ceil((it.salary)/5000)}
>                  ```

* b) Get a count of the number of employees in each department

>```groovy
>list.groupBy{it.DepartmentName}.each{ it.value=it.value.size()}
>```

* c) Get the list of employees whose age is between 18 and 35

>```groovy
>list.groupBy{ if(it.Age>=18 && it.Age<=35)
>                 return 0
>                 else
>                  return 1}[0]
>                  ```

* d) Group the employees according to the alphabet with which their first name starts and display the number of employees in each group whose age is greater than 20

>```groovy
>list.groupBy{ it.Name[0]}
>```

* e) Group the employees according to their department.

>```groovy
>list.groupBy{ it.DepartmentName}
>```

---




**Question24.**  Write a method which retruns the value of passed key from a search string of the form

**Answer**
>```groovy
>map=[1:"ashish",2:"patel",3:"is",4:"good"]
>findValue={key,str->
>            list=str.tokenize()
>            list.find{map[key]==it}}
>println findValue(2,"ashish patel is a good")
>```

**Question25.**  Write a method which retruns the value of passed key from a search string of the form 
`"http://www.google.com/?name=johny&age=20&hobby=cricket"`

**Answer**
>```groovy
>findValue={key,str->
>            list=str.tokenize('?')
>            (list[1].tokenize('&').find{ temp=it.tokenize('=')
>                                        if(temp[0]==key)
>                                           return temp[1]}.tokenize('='))[1]}
>println findValue("name","http://www.google.com/?name=johny&age=20&hobby=cricket")
>```