
**项目编码规范**

## 第一原则：编写详细的代码注释
- 每个变量的含义
- 每个条件分支的含义
- 每个代码块的含义
- 方法（函数）注释
  * 该方法的详细说明：用途、设计思路等
  * 每个参数的数据类型、取值范围、含义
  * 每个返回值的数据类型、取值范围、含义
  * 每个抛出的异常的触发愿意

## 第二原则：每个方法（函数）都要有一一对应的测试用例

## 其他编码规范
- 方法（函数）中的第1段代码必须是对输入参数的合法性检查。能用assert(断言)尽量
- 代码中不允许使用print，必须用logger打日志
- 变量长度不能小于3，且必须能读懂，可以使用拼音
- 使用f-strings构造动态字符串，不能使用 '+', format() 等方式
- 不能使用 from xxx import *
- 涉及系统资源的代码，要使用try/catch/finally或with进行管理。例如：文件操作、DB连接、网络连接等
- 统一使用python 3.6.9、统一使用utf-8、全局变量统一使用大写

- 最终的代码，要在pycharm中，尽量解决所有PEP8的建议
