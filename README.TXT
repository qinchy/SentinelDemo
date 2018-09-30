--sentinel-dashboard
1.启动sentinel-dashboard
D:\.m2\repository\com\alibaba\csp\sentinel-dashboard\0.1.1>java -Dserver.port=8081 -Dcsp.sentinel.dashboard.server=localhost:8081 -jar sentinel-dashboard-0.1.1.jar
2.访问http://localhost:8081/#/dashboard/home进入sentinel控制台，可以针对每一个应用进行流控









--应用程序
1.新建springboot程序
2.引入如下关键包
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-alibaba-sentinel</artifactId>
            <version>0.2.0.BUILD-SNAPSHOT</version>
        </dependency>
这个dependency需要自己编译后install到本地仓库
源码地址：git@github.com:qinchy/spring-cloud-alibaba.git
3.application.properties中新增如下配置
spring.application.name=sentineldemo
csp.sentinel.dashboard.server=localhost:8081
4.启动springboot程序
#jvm参数添加如下变量，指明sentinel-dashboard的地址
#-Dcsp.sentinel.dashboard.server=localhost:8081
5.页面访问
http://127.0.0.1:8080/sentineldemo/test/flowctl，会自动在sentinel-dashboard中注册


--流控规则
1.可以通过api来设置
2.可以通过流控dashboard来设置