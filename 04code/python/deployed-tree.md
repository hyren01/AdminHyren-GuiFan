
# 目录结构

```ini
[root dir]                        # 如果部署在Docker容器，默认为'/opt/app'。
|-- hrapp                         # 
|   |-- bin                       # shell脚本。项目启动的脚本、容器管理的脚本等等
|   |-- dist                      # 项目的发行包（jar或python源码）
|   |-- logs                      # 项目的日志输出根目录。
|   |-- resources                 # 资源文件根目录。包括 fdconfig, module, pretrain 等
|   |-- progout                   # 程序代码中需要的各种输出根目录

```
