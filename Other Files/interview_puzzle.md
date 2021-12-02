# Interview questions

## Queues and stacks

* Describe the difference between a stack and a queue. (5 points)
* Describe a typical programming use for a queue. (5 points) (需要以代码解释吗？)

## Linked lists

* Use C++ to show the structure of an element in a doubly linked list in which each element holds a single character.  Describe briefly what any pointers point to. (4 points) 
* Use C++ to show the operations necessary to insert a list element given a pointer to the new element and a pointer to the element after which the new element needs to be inserted. (6 points) 
(确定)

## Binary trees  

* Use C++ to show the structure of an element of a sorted, binary tree in which each element contains a single character.  Describe briefly what any pointers point to. (4 points)
* Use C++ to show the operations necessary to locate the element in the sorted binary tree which matches a given character. (6 points)

## C++ specifics

* Compare the following function and macro definitions.  In what cases will they produce different results and/or side effects? (5 points) 

```
int square(int val) { return val*val; }
#define square(val) (val*val)
```

## ConvertStringToInt

* Write a C++ function which converts a character string into a signed integer without using any library functions. Assume that the string contains a valid integer, and no white space. (10 points) 

```
// example of how the function you write would be used 
int val = ConvertStringToInt("-640"); // val would end up with the integer value -640 in it 
```

## C++ specifics

Given the following C++ String class and its defined operations, list the String operations that are called from function Test() in the order they are called. Assume the four unimplemented functions are implemented elsewhere. (5 points) 

```
class String 
{ 
public: 
    String() { m_str = new char[1]; *m_str = 0; }
    ~String();
    String(const char* str);
    String(const String& other);
    String& operator = (const String& other);

private:
    char* m_str;
}; 

 
String Func(String str1) 
{ 
    String str2;
    str2 = str1; 
    return str2; 
}

void Test() 
{ 
    String str3("Hello"); 
    str3 = Func(str3); 
} 
```
 
* Write the assignment operator for the String class defined above. Keep in mind the memory management assumptions implied by the implementation of the default constructor defined above. (10 points) 

```
String& String::operator= (const String& other) {

}
```

## 2D and 3D vectors

* Given a 2D vector A in the x-y plane of length |A| and angle theta to the x-axis, give the equations for the x and y components of A. (4 points) 
* Given the x,y,z components of a 3D vector A, give the equation for the angle between the vector and the x-y plane. (6 points)

## Physics

* Given a 3D point starting at position P1 and moving with constant velocity vector V, write an equation for the position P2 of the point after elapsed time t. (5 points)
* Given a 3D point starting at position P1 and moving with initial velocity vector V and constant acceleration vector A, write an equation for the position P2 of the point after elapsed time t. (7 points) 

## What does it do?

* Examine the following function. What does it accomplish? (8 points) 

```
int foo(int val)
{
    int n=0;
    while (val)
    {
        val &= val-1;
        n++;
    }
    return n;
}
```

## Palettes

* Describe what is meant by a "4-bit palette image". (4 points) 
* Describe what is meant by a "24-bit true-color image". (4 points) 
* How many shades of gray can be displayed in a 24-bit color image? (2 points) 

## General engineering

* Describe the major benefits of data-oriented design. (5 points)
* Describe the advantage of Entity-Component-Systems over object-oriented class hierarchies. (5 points)

# Shader optimization

* Describe a simple optimization for the following shader (5 points)

```
float3 diff; // 0 or 1
float4 someValue;
if (diff.x == 1.0 || diff.y == 1.0 || diff.z == 1.0)
    return someValue;
else
    return float4(0.0);
```