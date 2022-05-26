<center><h1>2020-2021学年第2学期 实 验 报 告</h1></center>

![zucc](README.assets/zucc.png)



<div style="margin-left:350px">- 课程名称：编程语言原理与编译</div>
<div style="margin-left:350px">- 实验项目：MicroC</div>
<div style="margin-left:350px">- 专业班级：计算机1803</div>
<div style="margin-left:350px">- 学生学号：31901061</div>
<div style="margin-left:350px">- 学生姓名：张泽峰</div>
<div style="margin-left:350px">- 实验指导教师: 郭鸣</div>



------



## 一、实验简介

​	本次大作业主要在原有工具Micro-C的基础上进行修改。通过对解释器和编译器的代码改进和开发，实现了部分C语言的语法。



## 二、项目说明

#### （一）结构

- 前端：由`F#`语言编写而成  
  - `CubyLex.fsl`生成的`CubyLex.fs`词法分析器。
  - `CubyPar.fsy`生成的`CubyPar.fs`语法分析器。
  - `AbstractSyntax.fs` 定义了抽象语法树
  - `Assembly.fs`定义了中间表示的生成指令集
  - `Compile.fs`将抽象语法树转化为中间表示
- 后端：由`Java`语言编写而成
- 测试集：测试程序放在`testing`文件夹内
- 库：`.net`支持
  - `FsLexYacc.Runtime.dll`



#### （二）用法

- `fslex --unicode CubyLex.fsl`  
  生成`CubyLex.fs`词法分析器
- `fsyacc --module CubyPar CubyPar.fsy`  
  生成`CubyPar.fs`语法分析器与`CubyPar.fsi`  
- `javac Machine.java`  
  生成虚拟机
- `fsi -r FsLexYacc.Runtime.dll AbstractSyntax.fs CubyPar.fs CubyLex.fs Parse.fs Assembly.fs Compile.fs ParseAndComp.fs`  
  可以启用`fsi`的运行该编译器。
- 在`fsi`中输入:  
  `open ParseAndComp;;`
- 之后则可以在`fsi`中使用使用：  

  - `fromString`：从字符串中进行编译

  - `fromFile`：从文件中进行编译

  - `compileToFile`：生成中间表示



