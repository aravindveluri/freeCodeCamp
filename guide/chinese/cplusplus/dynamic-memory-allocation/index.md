---
title: Dynamic Memory Allocation
localeTitle: 动态内存分配
---
## C ++中的动态内存分配

### 什么是C ++中的动态内存分配？

*   C ++中的**内存分配**是指**分配**给整个程序中使用的变量的内存。
*   **动态内存分配**是在运行时**分配**给变量的内存，所需的内存量也在运行时决定。
*   这个内存来自**堆** ，而非_静态_变量和_局部_变量从**堆栈中**获取内存。
*   在C ++中，程序员可以手动执行内存分配，并称为**_动态内存分配_** 。
*   在C中可以通过使用_calloc_和_malloc_函数来分配内存并使用_自由_函数来_解除_动态内存的分配来进行动态内存分配。
*   在C ++中，除了上述之外，还有两个函数， _new_和_delete，_用于执行动态内存分配和解除分配。

### 新运营商

*   `new`运算符可以从堆中授予程序员内存（如果可用）。如果程序员请求的存储器可用，则`new`运算符初始化存储器，然后返回分配的存储器的地址（引用）。
*   **句法**  
    `pointer-variable-type` = **new** `data-type;`  
    示例1： `int *ptr` = **new** `int;`  
    例2： `int *ptr2` = **new** `int[10];`  
    这里， `pointer-variable-type`是`data type`的**指针** 。 `data-type`可以是int，char等，也可以是用户定义的数据类型。

### DELETE运算符

*   程序员有责任解除分配动态分配的内存，否则在程序结束之前内存将无法重新分配。
    
*   要取消分配内存， `delete`操作符可用，程序员可以使用。
    
*   **句法**  
    **delete** `pointer-type-variable;`  
    例如，要释放上面示例1中分配的内存，我们键入：  
    `delete ptr;`  
    类似地，例如2，可以通过以下方式释放内存：  
    `delete ptr2` ;
    
    ### 内存泄漏
    
    当您无法释放在程序结束时通过`New`运算符分配的动态内存时，会导致泄漏。如果不使用Delete运算符取消分配，则每次程序运行时，计算机都将继续在堆中创建新内存。这会导致计算机速度变慢，因为内存未被删除且可用内存减少。