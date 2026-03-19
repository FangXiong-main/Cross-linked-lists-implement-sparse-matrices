十字链表实现稀疏矩阵存储与转置

Orthogonal List for Sparse Matrix Storage & Transposition
项目简介

本项目采用 C++ 语言实现 ** 十字链表（Orthogonal List）** 数据结构，专为稀疏矩阵量身打造，解决传统二维数组存储稀疏矩阵导致的内存浪费问题。完整实现稀疏矩阵的动态创建、控制台打印、矩阵转置以及内存销毁功能，是数据结构中链式存储的经典实践，适合课程设计、算法学习与源码研读。
This project implements the Orthogonal List data structure in C++, specifically designed for sparse matrices to solve the memory waste caused by traditional 2D array storage. It fully supports dynamic creation, console printing, matrix transposition and memory destruction of sparse matrices, which is a classic practice of linked storage in data structures, suitable for curriculum design, algorithm learning and source code research.

#核心功能
##十字链表节点定义，行 + 列双向链式存储稀疏矩阵
手动输入矩阵行列数与元素，自动跳过零元素节省内存
原始矩阵格式化打印，控制台直观展示矩阵结构
矩阵转置运算，快速实现行列互换
完整内存释放，避免内存泄漏

Orthogonal List node definition, bidirectional linked storage of sparse matrices by row & column
Manually input matrix rows, columns and elements, automatically skip zero elements to save memory
Formatted printing of original matrix, intuitively display matrix structure in console
Matrix transposition operation, quickly realize row-column exchange
Complete memory release to avoid memory leaks

#项目结构
##Orthogonal-List-Sparse-Matrix/
├── main.cpp       # 核心源码文件（结构定义+功能实现）
└── README.md      # 项目说明文档
数据结构

节点定义

采用十字链表节点存储稀疏矩阵非零元素，每个节点包含行号、列号、元素值，以及行方向（Right）、列方向（Down）指针，同一行非零元素通过 Right 指针串联，同一列非零元素通过 Down 指针串联，仅存储非零元素，大幅提升内存利用率。
Orthogonal List nodes are used to store non-zero elements of sparse matrices. Each node contains row number, column number, element value, row-direction (Right) and column-direction (Down) pointers. Non-zero elements in the same row are connected by Right pointers, and non-zero elements in the same column are connected by Down pointers. Only non-zero elements are stored, greatly improving memory utilization.
cpp


运行




typedef class Matrix_Node
{
public :
    int line;        // 行号 / Row number
    int row;         // 列号 / Column number
    Element Ele;     // 元素值 / Element value
    Matrix_Node * Down;   // 列指针 / Column pointer
    Matrix_Node * Right;  // 行指针 / Row pointer
}Node;
编译运行

中文步骤

使用 C++ 编译器（g++、VS、Clion 等）编译main.cpp文件
运行生成的可执行文件，按照控制台提示输入矩阵行数、列数
依次输入每个位置元素，输入 0 代表该位置无有效元素（不存储）
程序自动打印原始矩阵，执行转置后打印转置矩阵
根据提示选择是否销毁原始矩阵，释放内存
English Steps

Compile main.cpp with a C++ compiler (g++, VS, Clion, etc.)
Run the generated executable, input matrix rows and columns as prompted
Input elements of each position in turn, entering 0 means no valid element (not stored)
The program automatically prints the original matrix, and prints the transposed matrix after transposition
Choose whether to destroy the original matrix and release memory as prompted
Linux/Mac 编译命令

bash


运行




g++ main.cpp -o SparseMatrix
./SparseMatrix
注意事项

输入 0 元素不会被存储，仅作为占位符展示，贴合稀疏矩阵存储逻辑
矩阵转置会新建十字链表结构，不修改原始矩阵数据
适用于非零元素远少于零元素的稀疏矩阵场景
Input 0 elements will not be stored, only displayed as placeholders, conforming to sparse matrix storage logic
Matrix transposition creates a new Orthogonal List structure without modifying the original matrix data
Suitable for sparse matrix scenarios where non-zero elements are far fewer than zero elements
适用场景

数据结构课程设计
链式存储结构学习与实践
稀疏矩阵算法入门
C++ 指针与内存管理练习
Data Structure Curriculum Design
Linked Storage Structure Learning & Practice
Sparse Matrix Algorithm Introduction
C++ Pointer & Memory Management Practice
