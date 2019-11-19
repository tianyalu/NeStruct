## NeStruct 结构体
### 一、结构体
#### 1.1 结构体
当结构体需要内存过大，使用动态内存申请。结构体所占用字节数和结构体内字段有关，指针所用内存就是4/8字节，因此传指针比传值效率更高。
#### 1.2 结构体存储原则
* 结构体变量中成员的偏移量必须是成员大小的整数倍（0被认为是任何数的整数倍）
* 结构体大小必须是所有成员大小的整数倍，也即所有成员大小的公倍数 

#### 1.3 代码
```c
struct Student {
    int i;
    short j;
}s1, s2;

int main(int argc, const char * argv[]) {
    struct Student student;
    student.i = 10;
    student.j = 5;
    s1.i = 11;
    s1.j = 2;
    
    printf("当前结构体大小：%ld\n", sizeof(student)); //8
    printf("student i = %d, j = %hd\n", student.i, student.j ); //10,5
    printf("s1 i = %d, j = %hd\n", s1.i, s1.j ); //11,2
    
    return 0;
}
```
### 二、内存对齐
对齐跟数据在内存中的位置有关。如果一个变量的内存地址正好位于它长度的整数倍，它就被称为自然对齐。比如在32位CPU下，假设一个整型变量的
地址为0x00000004,那么它就是自然对齐的。  
![image](https://github.com/tianyalu/NeStruct/blob/master/show/memory_align.png)

