
## 背景

很多时候项目代码在运行时需要使用到账号、密码、key等敏感数据信息，但是从信息安全的角度考虑，我们是不能将这些敏感数据提交到代码仓库的，主要原因有两个：

- 加强权限管控：参与项目的开发人员可能会有很多，大家都有读取代码仓库的权限，但是像 key 这类极度敏感的信息不应该所有人都有权限获取；
- 减少代码泄漏的危害性：假如代码出现泄漏，敏感数据信息不应该也同时泄漏。

## 解决方案

那代码部署到服务器或 Jenkins 执行机后，运行时要使用到这些敏感数据信息，该怎么操作呢？

推荐的操作方式为：

- 对服务器进行权限管控，只有运维人员（或者核心开发人员）才有登录服务器的权限；
- 运维人员（或者核心开发人员）：在运行的机器上将敏感数据设置到系统的环境变量中；
- 普通开发人员：只需要知道敏感信息的变量名称，在代码中通过读取环境变量的方式获取敏感数据。

存储敏感数据（设置环境变量）和使用敏感数据（引用环境变量）的具体方法，可参考[环境变量](/advanced/dot-env/)使用说明文档。
