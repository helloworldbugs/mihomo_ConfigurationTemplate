# mihomo_ConfigurationTemplate

# 说明

这几天有空花时间研究了一下mihomo的规则配置，写了几份mihomo配置文件模板出来，在每个重要的字段都写了中文注释便于理解与学习

使用的域名和ip库是使用官方推荐的提供方

# 使用说明

以前一直都在使用第三方的客户端，启动速度慢不说，关键是还占位置占内存，经过学习，发现直接使用官方的内核就很方便使用了

直接在[mihomo官网](https://github.com/MetaCubeX/mihomo)下载所需的可执行文件内核，把配置文件 config.yaml 和内核放在一个目录，然后命令执行 `mihomo.exe -d .` （win平台为例）就可以了，其它的一切在第三方gui客户端上的配置，都可以在配置文件里修改，当然也可以访问[后台UI管理平台](http://localhost:9090/ui) `http://localhost:9090/ui` 进行修改和控制

至于Windows怎么隐藏命令行窗口启动，这个就不再赘述，方法多的是。可以用 vbs 脚本，也可以用 winsw 注册成服务
