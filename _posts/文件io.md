---
title: 文件io
---

## 打开文件

```c++
/***
*	istream 输入文件类型
* 	ifile 文件标识符
*   param ./demo.text 文件路径
*	ios::in 打开的文件状态为获取文件的类容
*	当文件不存在时，会创建一个新的文件
*/
istream ifile("./demo.txt",ios::in);//该文件可读


ostream ofile("./dest.txt".io::out);//该文件可写
```

## 获取文件内容

### 从文件中获取字符串

```c++
string buf;
ifile >> buf;
```

### 从文件中获取结构体数据

```c++
operate>>(fstream& ifile ,struct temp)//重载>>双目运算符
{
    ifile >> temp.a;
    ifile >> temp.b;
}
```

## 写入文件操作

## 将字符串写入文件中

```c++
string buf;
ofile << buf;
```

## 将结构体数据写入文件中

```c++
operate<<(fstream& ofile ,struct temp)//重载<<双目运算符
{
    ofile << temp.a;
    ofile << temp.b;
}
```

