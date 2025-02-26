```bash
mkdir 02_Array
ls
```  
#### Output:  
```bash
01_Intro  02_Array
```  
```bash
cd 02_Array/
```  
now lets create first array script which demonstrate array  
in most of programming language arrays elements are seperated by `qoma (,)` but in shell scripting its seperated by `whitespace ( )`  
```bash
vi 01_array_demo.sh
```  
inside it  
```bash
#!/bin/bash
myArr=(1 2.5 Hello "Batman")
echo "The entire array is: ( ${myArr[*]})"
echo "${myArr[0]}"
echo "${myArr[1]}"
echo "${myArr[2]}"
heroName=${myArr[3]}
echo "the name if hero is $heroName"
myArrLength=${#myArr[*]}
echo "The length of this array is: $myArrLength"
twoValuesAfterFirstIndex=${myArr[*]:1:2}
echo "Two elements after 1st index: ${twoValuesAfterFirstIndex}"
```  
#### Output:  
```vbnet
The entire array is: ( 1 2.5 Hello Batman)
1
2.5
Hello
the name if hero is Batman
The length of this array is: 4
Two elements after 1st index: 2.5 Hello
```  