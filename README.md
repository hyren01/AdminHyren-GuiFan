# 各目录说明
- 04code 存放python,java等编码规范


## 主机部署结构
```ini
[root dir]                               # 客户给我们使用的根目录。
|--hrsapp                                # 项目根目录
|    |-- bin                             # shell脚本，其他需要使用的脚本，比如：因客户需求需要额外提供的脚本
|    |-- dist                            # 项目的发行包根目录（jar或python源码）
|    |    |-- python                     # python开发语言
|    |    |    |-- [project name]        # 项目名称。例如：jdqd。整个结构与git上一致
|    |    |    |    |-- common           # 该项目范围内的公共方法归属包
|    |    |    |    |-- a01              # 子系统名称
|    |    |    |    |  |-- event_match   # 模块名称
|    |    |    |    |-- a03              # 子系统名称
|    |    |    |    |  |-- event_pred    # 模块名称
|    |    |    |    |-- a04              # 子系统名称
|    |    |    |-- resources             # python项目所需的资源目录。包括 fdconfig, module, pretrain等
|    |    |-- java                       # java开发语言
|    |    |    |-- [A]                   # 后端各子系统名字。例如海云的A, B, K, Agent等等。如果没有子系统，则取名把backend
|    |    |    |    |-- lib              # 项目所需的jar目录，创建软连接至GlobalShared目录
|    |    |    |    |-- resources        # java项目所需的资源目录。包括，fdconfig，i18n, uploadfiles等
|    |    |    |    |-- A.jar            # 项目所需执行的jar文件
|    |    |    |-- GlobalShared          # java存放全局共享的资源。对其建立一个独立容器，被其他容器挂载使用
|    |    |    |    |-- jdklibs          # java项目中，全局共享使用的jar文件
|    |    |    |    |-- [...]            # 根据实际情况，建立更多的目录
|    |    |-- vue                        # 前端
|    |    |    |-- favicon.ico           # 前端网站图标
|    |    |    |-- index.html            # 前端主页html文件
|    |    |    |-- static                # 前端的发行包（源码)
|    |    |-- shell                      # 启动容器脚本，项目启动的脚本、容器管理的脚本
|    |    |    |-- fd_utils.sh           # 所有脚本必须包含的公共函数
|    |-- logs                            # 项目的日志输出根目录。
|    |-- progout                         # 程序代码需要输出文件时，存放的根目录
```

## 容器部署结构
```ini
[root dir]                               # 客户给我们使用的根目录，部署在Docker容器，默认为'/opt'
|--hrsapp                                # 项目根目录。
|    |-- bin                             # shell脚本，其他需要使用的脚本，比如：因客户需求需要额外提供的脚本
|    |-- dist                            # 项目的发行包根目录（jar或python源码）
|    |    |-- java                       # java开发语言
|    |    |    |-- [A]                   # 后端各子系统名字。例如海云的A, B, K, Agent等等。如果没有子系统，则取名把backend
|    |    |    |   |-- lib               # 项目所需的jar目录
|    |    |    |   |-- resources         # java项目所需的资源目录。包括fdconfig，i18n, uploadfiles等
|    |    |    |   |-- [A.jar]           # 项目所需执行的jar文件
|    |    |    |-- GlobalShared          # java存放全局共享的资源。对其建立一个独立容器，被其他容器挂载使用
|    |    |    |   |-- jdklibs           # java项目中，全局共享使用的jar文件
|    |    |    |   |-- [...]             # 根据实际情况，建立更多的目录
|    |    |-- python                     # python开发语言
|    |    |    |-- [project name]        # 项目名称。例如：jdqd。整个结构与git上一致
|    |    |    |   |-- common            # 该项目范围内的公共方法归属包
|    |    |    |   |-- a01               # 子系统名称
|    |    |    |   |   |-- event_match   # 模块名称（jar或python源码）
|    |    |    |   |   |     |-- algor   # 项目的发行包（python源码）
|    |    |    |   |   |     |-- ...     # 项目的发行包（python源码）
|    |    |    |-- resources             # python项目所需的资源目录。包括 fdconfig, module, pretrain等
|    |    |-- shell                      # 启动容器脚本，项目启动的脚本、容器管理的脚本
|    |    |    |-- fd_utils.sh           # 所有脚本必须包含的公共函数
|    |    |-- vue                        # 前端
|    |    |    |-- favicon.ico           # 前端网站图标
|    |    |    |-- index.html            # 前端主页html文件
|    |    |    |-- static                # 前端的发行包（源码)
|    |-- logs                            # 项目的日志输出根目录。
|    |-- progout                         # 程序代码需要输出文件时，存放的根目录
```

无论是Docker部署，还是本地部署，都要使用以上目录结构。
