
# 目录结构

```ini
|-- README.md
|-- TODO.md
|-- docs                          # 所有其他md说明文档
|-- [project name]                # 项目名，全小写。拼音或英文。对应pycharm工程下的第一级目录
|   |-- common                    # 该工程范围内的公共方法归属包
|   |-- [module name]             # 模块名，全小写。只能使用a01, b02
|   |   |-- algor                 # 仅仅用于'训练和预测'场景的算法程序。
|   |   |   |-- predict           #
|   |   |   |-- train             #
|   |   |   |-- common            #
|   |   |-- services              # 所有业务处理功能归属的顶级包
|   |   |   |-- [func name]       # 功能名，全小写。a0101, b0102，或者使用拼音或英文
|   |   |   |-- common            # 本模块内，公共的方法
|   |   |-- restapp               # 存放对外http接口的程序包
|   |   |   |-- ......            #  
|   |   |-- config                # 本模块内共享使用的配置参数
|   |   |   |-- algor.py          #
|   |   |   |-- services.py       #
|   |   |-- requirements.txt      # 本模块需要的依赖包
|   |   |-- README.md             # 本模块的使用说明。例如rest接口的访问方式、输入和返回
|   |-- webapp                    # 用于存放应用端后端程序包顶级主目录
|   |   |-- services              # 所有业务处理功能归属的顶级包
|   |   |   |-- [func name]       # 功能名，全小写。a0101, b0102，或者使用拼音或英文
|   |   |   |-- common            # 本模块内，公共的方法
|   |   |-- restapp               # 存放对外http接口的程序包
|   |   |   |-- ......            #  
|   |   |-- config                # 本模块内共享使用的配置参数
|   |   |   |-- algor.py          #
|   |   |   |-- services.py       #
|   |   |-- requirements.txt      # 本模块需要的依赖包
|   |   |-- README.md             # 本模块的使用说明。例如rest接口的访问方式、输入和返回
|-- resources                     # 
|   |-- fdconfig                  # 所有在不同运行环境下需要动态修改的配置信息
|   |   |-- appinfo.conf          # 
|   |   |-- dbinfo.conf           # 
|   |-- module                    # 训练好的模型文件的存放根目录。下面用模块名创建子目录
|   |   |-- [module name]         # 存放该模块训练出来的模型文件
|   |-- pretrain                  # 依赖的预训练模型
|   |-- ......                    # 其他本项目需要的东西（自定义）
|-- test_suite                    # 测试用例代码。
|   |-- [module name]             # 与被测试模块一一对应
|   |   |-- algor                 # 
|   |   |-- services              #
|-- requirements.txt              # 整个项目需要的全部依赖包（各模块的汇总）
```