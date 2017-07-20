# Goods_CRUD

建立Maven项目，添加maven模块，将其中的server部分转换成web模块，

##在总的pom中添加依赖
详见总的pom.xml


##core层添加相应的依赖，
详见core层的pom.xml


启动后可以看到

......
beginTestJob
2017-07-17 16:30:30,527 [localhost-startStop-1] INFO org.springframework.web.context.ContextLoader - Root WebApplicationContext: initialization completed in 456 ms
.......
2017-07-17 16:30:30,529 [org.springframework.scheduling.quartz.SchedulerFactoryBean#0_Worker-1] DEBUG org.quartz.core.JobRunShell - Calling execute on job DEFAULT.org.springframework.scheduling.quartz.MethodInvokingJobDetailFactoryBean#1e94e858
Test quartz
七月 17, 2017 4:30:30 下午 org.apache.catalina.startup.HostConfig deployDirectory
信息: Deploying web application directory D:\WorkSpace\JAVAWorkSpace\HDTomcat\apache-tomcat-7.0.42\webapps\ROOT
七月 17, 2017 4:30:30 下午 org.apache.coyote.AbstractProtocol start
信息: Starting ProtocolHandler ["http-apr-8080"]
七月 17, 2017 4:30:30 下午 org.apache.coyote.AbstractProtocol start
信息: Starting ProtocolHandler ["ajp-apr-8009"]
七月 17, 2017 4:30:30 下午 org.apache.catalina.startup.Catalina start
信息: Server startup in 1678 ms
2017-07-17 16:30:35,002 [org.springframework.scheduling.quartz.SchedulerFactoryBean#0_Worker-2] DEBUG org.quartz.core.JobRunShell - Calling execute on job DEFAULT.org.springframework.scheduling.quartz.MethodInvokingJobDetailFactoryBean#1e94e858
Test quartz
2017-07-17 16:30:40,002 [org.springframework.scheduling.quartz.SchedulerFactoryBean#0_Worker-3] DEBUG org.quartz.core.JobRunShell - Calling execute on job DEFAULT.org.springframework.scheduling.quartz.MethodInvokingJobDetailFactoryBean#1e94e858
Test quartz

看到"Test quartz"持续输出证明定时任务启动


##整合cxf，提供restful接口，输入<code>http://localhost:8080/goods-server/rest</code>

可以得到如下界面
![alt text](https://github.com/kingflag/Goods_CRUD/blob/master/src/site/restful-success.jpg "restful请求成功")

输入<code>http://localhost:8080/goods-server/rest/core/con/func</code>
访问restful的url的结果
![alt text](https://github.com/kingflag/Goods_CRUD/blob/master/src/site/restful-result.jpg "restful请求得到的结果")

集成JPA之后，可在输出台看到数据库信息和插入数据的显示
![alt text](https://github.com/kingflag/Goods_CRUD/blob/master/src/site/JPA-info.jpg "jpa集成成功后可以看到的图片")

实现RS层与core层的数据交互
访问<code>http://localhost:8080/goods-server/rest/core/goodshandle/querybyid/12</code>
![alt text](https://github.com/kingflag/Goods_CRUD/blob/master/src/site/rs-core.jpg "实现RS层与core层的数据交互")

