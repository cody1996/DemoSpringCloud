This is a minimal sample for [this issue](https://github.com/spring-cloud/spring-cloud-netflix/issues/2756).

Run `EurekaServer` first, then run `HelloService`. (One instance each is enough, just use my `.yml` files)

After about one minute, this error will appear in the console of the `HelloService`.

My console output is as follows:

```
2018-04-05 17:57:20.093  INFO 7576 --- [           main] s.c.a.AnnotationConfigApplicationContext : Refreshing org.springframework.context.annotation.AnnotationConfigApplicationContext@37afeb11: startup date [Thu Apr 05 17:57:20 CST 2018]; root of context hierarchy
2018-04-05 17:57:20.251  INFO 7576 --- [           main] f.a.AutowiredAnnotationBeanPostProcessor : JSR-330 'javax.inject.Inject' annotation found and supported for autowiring
2018-04-05 17:57:20.286  INFO 7576 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'configurationPropertiesRebinderAutoConfiguration' of type [org.springframework.cloud.autoconfigure.ConfigurationPropertiesRebinderAutoConfiguration$$EnhancerBySpringCGLIB$$83cd5a2] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v2.0.0.RELEASE)

2018-04-05 17:57:21.878  INFO 7576 --- [           main] c.e.h.HelloServiceApplication            : The following profiles are active: dev
2018-04-05 17:57:21.887  INFO 7576 --- [           main] ConfigServletWebServerApplicationContext : Refreshing org.springframework.boot.web.servlet.context.AnnotationConfigServletWebServerApplicationContext@78d6692f: startup date [Thu Apr 05 17:57:21 CST 2018]; parent: org.springframework.context.annotation.AnnotationConfigApplicationContext@37afeb11
2018-04-05 17:57:22.348  INFO 7576 --- [           main] o.s.b.f.s.DefaultListableBeanFactory     : Overriding bean definition for bean 'environmentWebEndpointExtension' with a different definition: replacing [Root bean: class [null]; scope=; abstract=false; lazyInit=false; autowireMode=3; dependencyCheck=0; autowireCandidate=true; primary=false; factoryBeanName=org.springframework.boot.actuate.autoconfigure.env.EnvironmentEndpointAutoConfiguration; factoryMethodName=environmentWebEndpointExtension; initMethodName=null; destroyMethodName=(inferred); defined in class path resource [org/springframework/boot/actuate/autoconfigure/env/EnvironmentEndpointAutoConfiguration.class]] with [Root bean: class [null]; scope=; abstract=false; lazyInit=false; autowireMode=3; dependencyCheck=0; autowireCandidate=true; primary=false; factoryBeanName=org.springframework.cloud.autoconfigure.LifecycleMvcEndpointAutoConfiguration$EndpointConfiguration; factoryMethodName=environmentWebEndpointExtension; initMethodName=null; destroyMethodName=(inferred); defined in class path resource [org/springframework/cloud/autoconfigure/LifecycleMvcEndpointAutoConfiguration$EndpointConfiguration.class]]
2018-04-05 17:57:22.557  INFO 7576 --- [           main] o.s.cloud.context.scope.GenericScope     : BeanFactory id=0bd1adfa-0a3e-34a7-ad23-834183ca5bcd
2018-04-05 17:57:22.573  INFO 7576 --- [           main] f.a.AutowiredAnnotationBeanPostProcessor : JSR-330 'javax.inject.Inject' annotation found and supported for autowiring
2018-04-05 17:57:22.659  INFO 7576 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'org.springframework.cloud.autoconfigure.ConfigurationPropertiesRebinderAutoConfiguration' of type [org.springframework.cloud.autoconfigure.ConfigurationPropertiesRebinderAutoConfiguration$$EnhancerBySpringCGLIB$$83cd5a2] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2018-04-05 17:57:22.910  INFO 7576 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2018-04-05 17:57:22.928  INFO 7576 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2018-04-05 17:57:22.928  INFO 7576 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet Engine: Apache Tomcat/8.5.28
2018-04-05 17:57:22.932  INFO 7576 --- [ost-startStop-1] o.a.catalina.core.AprLifecycleListener   : The APR based Apache Tomcat Native library which allows optimal performance in production environments was not found on the java.library.path: [C:\Program Files\Java\jdk1.8.0_162\bin;C:\WINDOWS\Sun\Java\bin;C:\WINDOWS\system32;C:\WINDOWS;C:\ProgramData\Oracle\Java\javapath;C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\Program Files (x86)\Pandoc\;C:\Program Files\Git\cmd;D:\AppData\Android\sdk\platform-tools;C:\Users\cody\AppData\Local\Microsoft\WindowsApps;C:\Program Files\Microsoft VS Code\bin;C:\Users\cody\AppData\Local\atom\bin;.]
2018-04-05 17:57:23.115  INFO 7576 --- [ost-startStop-1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2018-04-05 17:57:23.116  INFO 7576 --- [ost-startStop-1] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 1229 ms
2018-04-05 17:57:24.869  INFO 7576 --- [ost-startStop-1] o.s.cloud.commons.util.InetUtils         : Cannot determine local hostname
2018-04-05 17:57:26.310  INFO 7576 --- [ost-startStop-1] o.s.cloud.commons.util.InetUtils         : Cannot determine local hostname
2018-04-05 17:57:26.781  INFO 7576 --- [ost-startStop-1] o.s.b.w.servlet.ServletRegistrationBean  : Servlet dispatcherServlet mapped to [/]
2018-04-05 17:57:26.786  INFO 7576 --- [ost-startStop-1] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'characterEncodingFilter' to: [/*]
2018-04-05 17:57:26.786  INFO 7576 --- [ost-startStop-1] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'hiddenHttpMethodFilter' to: [/*]
2018-04-05 17:57:26.786  INFO 7576 --- [ost-startStop-1] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'httpPutFormContentFilter' to: [/*]
2018-04-05 17:57:26.786  INFO 7576 --- [ost-startStop-1] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'requestContextFilter' to: [/*]
2018-04-05 17:57:26.786  INFO 7576 --- [ost-startStop-1] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'httpTraceFilter' to: [/*]
2018-04-05 17:57:26.787  INFO 7576 --- [ost-startStop-1] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'webMvcMetricsFilter' to: [/*]
2018-04-05 17:57:26.918  WARN 7576 --- [           main] c.n.c.sources.URLConfigurationSource     : No URLs will be polled as dynamic configuration sources.
2018-04-05 17:57:26.918  INFO 7576 --- [           main] c.n.c.sources.URLConfigurationSource     : To enable URLs as dynamic configuration sources, define System property archaius.configurationSource.additionalUrls or make config.properties available on classpath.
2018-04-05 17:57:26.922  WARN 7576 --- [           main] c.n.c.sources.URLConfigurationSource     : No URLs will be polled as dynamic configuration sources.
2018-04-05 17:57:26.922  INFO 7576 --- [           main] c.n.c.sources.URLConfigurationSource     : To enable URLs as dynamic configuration sources, define System property archaius.configurationSource.additionalUrls or make config.properties available on classpath.
2018-04-05 17:57:27.191  INFO 7576 --- [           main] s.w.s.m.m.a.RequestMappingHandlerAdapter : Looking for @ControllerAdvice: org.springframework.boot.web.servlet.context.AnnotationConfigServletWebServerApplicationContext@78d6692f: startup date [Thu Apr 05 17:57:21 CST 2018]; parent: org.springframework.context.annotation.AnnotationConfigApplicationContext@37afeb11
2018-04-05 17:57:27.239  INFO 7576 --- [           main] s.w.s.m.m.a.RequestMappingHandlerMapping : Mapped "{[/hello],methods=[GET]}" onto public java.lang.String com.example.helloservice.HelloController.hello()
2018-04-05 17:57:27.243  INFO 7576 --- [           main] s.w.s.m.m.a.RequestMappingHandlerMapping : Mapped "{[/error]}" onto public org.springframework.http.ResponseEntity<java.util.Map<java.lang.String, java.lang.Object>> org.springframework.boot.autoconfigure.web.servlet.error.BasicErrorController.error(javax.servlet.http.HttpServletRequest)
2018-04-05 17:57:27.244  INFO 7576 --- [           main] s.w.s.m.m.a.RequestMappingHandlerMapping : Mapped "{[/error],produces=[text/html]}" onto public org.springframework.web.servlet.ModelAndView org.springframework.boot.autoconfigure.web.servlet.error.BasicErrorController.errorHtml(javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse)
2018-04-05 17:57:27.279  INFO 7576 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/webjars/**] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2018-04-05 17:57:27.279  INFO 7576 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/**] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2018-04-05 17:57:27.315  INFO 7576 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/**/favicon.ico] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2018-04-05 17:57:27.724  INFO 7576 --- [           main] s.b.a.e.w.s.WebMvcEndpointHandlerMapping : Mapped "{[/actuator/health],methods=[GET],produces=[application/vnd.spring-boot.actuator.v2+json || application/json]}" onto public java.lang.Object org.springframework.boot.actuate.endpoint.web.servlet.AbstractWebMvcEndpointHandlerMapping$OperationHandler.handle(javax.servlet.http.HttpServletRequest,java.util.Map<java.lang.String, java.lang.String>)
2018-04-05 17:57:27.725  INFO 7576 --- [           main] s.b.a.e.w.s.WebMvcEndpointHandlerMapping : Mapped "{[/actuator/info],methods=[GET],produces=[application/vnd.spring-boot.actuator.v2+json || application/json]}" onto public java.lang.Object org.springframework.boot.actuate.endpoint.web.servlet.AbstractWebMvcEndpointHandlerMapping$OperationHandler.handle(javax.servlet.http.HttpServletRequest,java.util.Map<java.lang.String, java.lang.String>)
2018-04-05 17:57:27.726  INFO 7576 --- [           main] s.b.a.e.w.s.WebMvcEndpointHandlerMapping : Mapped "{[/actuator],methods=[GET],produces=[application/vnd.spring-boot.actuator.v2+json || application/json]}" onto protected java.util.Map<java.lang.String, java.util.Map<java.lang.String, org.springframework.boot.actuate.endpoint.web.Link>> org.springframework.boot.actuate.endpoint.web.servlet.WebMvcEndpointHandlerMapping.links(javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse)
2018-04-05 17:57:27.805  INFO 7576 --- [           main] o.s.j.e.a.AnnotationMBeanExporter        : Registering beans for JMX exposure on startup
2018-04-05 17:57:27.823  INFO 7576 --- [           main] o.s.j.e.a.AnnotationMBeanExporter        : Bean with name 'configurationPropertiesRebinder' has been autodetected for JMX exposure
2018-04-05 17:57:27.824  INFO 7576 --- [           main] o.s.j.e.a.AnnotationMBeanExporter        : Bean with name 'environmentManager' has been autodetected for JMX exposure
2018-04-05 17:57:27.827  INFO 7576 --- [           main] o.s.j.e.a.AnnotationMBeanExporter        : Bean with name 'refreshScope' has been autodetected for JMX exposure
2018-04-05 17:57:27.830  INFO 7576 --- [           main] o.s.j.e.a.AnnotationMBeanExporter        : Located managed bean 'environmentManager': registering with JMX server as MBean [org.springframework.cloud.context.environment:name=environmentManager,type=EnvironmentManager]
2018-04-05 17:57:27.845  INFO 7576 --- [           main] o.s.j.e.a.AnnotationMBeanExporter        : Located managed bean 'refreshScope': registering with JMX server as MBean [org.springframework.cloud.context.scope.refresh:name=refreshScope,type=RefreshScope]
2018-04-05 17:57:27.866  INFO 7576 --- [           main] o.s.j.e.a.AnnotationMBeanExporter        : Located managed bean 'configurationPropertiesRebinder': registering with JMX server as MBean [org.springframework.cloud.context.properties:name=configurationPropertiesRebinder,context=78d6692f,type=ConfigurationPropertiesRebinder]
2018-04-05 17:57:27.884  INFO 7576 --- [           main] o.s.c.support.DefaultLifecycleProcessor  : Starting beans in phase 0
2018-04-05 17:57:27.891  INFO 7576 --- [           main] o.s.c.n.eureka.InstanceInfoFactory       : Setting initial instance status as: STARTING
2018-04-05 17:57:27.928  INFO 7576 --- [           main] com.netflix.discovery.DiscoveryClient    : Initializing Eureka in region us-east-1
2018-04-05 17:57:27.933  INFO 7576 --- [           main] c.n.d.s.r.aws.ConfigClusterResolver      : Resolving eureka endpoints via configuration
2018-04-05 17:57:28.152  INFO 7576 --- [           main] com.netflix.discovery.DiscoveryClient    : Disable delta property : false
2018-04-05 17:57:28.152  INFO 7576 --- [           main] com.netflix.discovery.DiscoveryClient    : Single vip registry refresh property : null
2018-04-05 17:57:28.152  INFO 7576 --- [           main] com.netflix.discovery.DiscoveryClient    : Force full registry fetch : false
2018-04-05 17:57:28.152  INFO 7576 --- [           main] com.netflix.discovery.DiscoveryClient    : Application is null : false
2018-04-05 17:57:28.152  INFO 7576 --- [           main] com.netflix.discovery.DiscoveryClient    : Registered Applications size is zero : true
2018-04-05 17:57:28.152  INFO 7576 --- [           main] com.netflix.discovery.DiscoveryClient    : Application version is -1: true
2018-04-05 17:57:28.152  INFO 7576 --- [           main] com.netflix.discovery.DiscoveryClient    : Getting all instance registry info from the eureka server
2018-04-05 17:57:28.424  INFO 7576 --- [           main] com.netflix.discovery.DiscoveryClient    : The response status is 200
2018-04-05 17:57:28.426  INFO 7576 --- [           main] com.netflix.discovery.DiscoveryClient    : Starting heartbeat executor: renew interval is: 30
2018-04-05 17:57:28.428  INFO 7576 --- [           main] c.n.discovery.InstanceInfoReplicator     : InstanceInfoReplicator onDemand update allowed rate per min is 4
2018-04-05 17:57:28.433  INFO 7576 --- [           main] com.netflix.discovery.DiscoveryClient    : Discovery Client initialized at timestamp 1522922248432 with initial instances count: 0
2018-04-05 17:57:28.437  INFO 7576 --- [           main] o.s.c.n.e.s.EurekaServiceRegistry        : Registering application hello-service with eureka with status UP
2018-04-05 17:57:28.437  INFO 7576 --- [           main] com.netflix.discovery.DiscoveryClient    : Saw local status change event StatusChangeEvent [timestamp=1522922248437, current=UP, previous=STARTING]
2018-04-05 17:57:28.439  INFO 7576 --- [nfoReplicator-0] com.netflix.discovery.DiscoveryClient    : DiscoveryClient_HELLO-SERVICE/localhost:hello-service:8080: registering service...
2018-04-05 17:57:28.481  INFO 7576 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2018-04-05 17:57:28.482  INFO 7576 --- [           main] .s.c.n.e.s.EurekaAutoServiceRegistration : Updating port to 8080
2018-04-05 17:57:28.484  INFO 7576 --- [           main] c.e.h.HelloServiceApplication            : Started HelloServiceApplication in 10.353 seconds (JVM running for 11.386)
2018-04-05 17:57:28.531  INFO 7576 --- [nfoReplicator-0] com.netflix.discovery.DiscoveryClient    : DiscoveryClient_HELLO-SERVICE/localhost:hello-service:8080 - registration status: 204
2018-04-05 17:57:29.058  INFO 7576 --- [on(2)-127.0.0.1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring FrameworkServlet 'dispatcherServlet'
2018-04-05 17:57:29.058  INFO 7576 --- [on(2)-127.0.0.1] o.s.web.servlet.DispatcherServlet        : FrameworkServlet 'dispatcherServlet': initialization started
2018-04-05 17:57:29.072  INFO 7576 --- [on(2)-127.0.0.1] o.s.web.servlet.DispatcherServlet        : FrameworkServlet 'dispatcherServlet': initialization completed in 14 ms
2018-04-05 17:57:58.428  INFO 7576 --- [freshExecutor-0] com.netflix.discovery.DiscoveryClient    : Disable delta property : false
2018-04-05 17:57:58.429  INFO 7576 --- [freshExecutor-0] com.netflix.discovery.DiscoveryClient    : Single vip registry refresh property : null
2018-04-05 17:57:58.429  INFO 7576 --- [freshExecutor-0] com.netflix.discovery.DiscoveryClient    : Force full registry fetch : false
2018-04-05 17:57:58.429  INFO 7576 --- [freshExecutor-0] com.netflix.discovery.DiscoveryClient    : Application is null : false
2018-04-05 17:57:58.430  INFO 7576 --- [freshExecutor-0] com.netflix.discovery.DiscoveryClient    : Registered Applications size is zero : true
2018-04-05 17:57:58.430  INFO 7576 --- [freshExecutor-0] com.netflix.discovery.DiscoveryClient    : Application version is -1: false
2018-04-05 17:57:58.430  INFO 7576 --- [freshExecutor-0] com.netflix.discovery.DiscoveryClient    : Getting all instance registry info from the eureka server
2018-04-05 17:57:58.476 ERROR 7576 --- [freshExecutor-0] c.n.d.s.t.d.RedirectingEurekaHttpClient  : Request execution error

org.springframework.web.client.RestClientException: Error while extracting response for type [class org.springframework.cloud.netflix.eureka.http.EurekaApplications] and content type [application/json]; nested exception is org.springframework.http.converter.HttpMessageNotReadableException: JSON parse error: Unrecognized field "overriddenStatus" (class com.netflix.appinfo.InstanceInfo), not marked as ignorable; nested exception is com.fasterxml.jackson.databind.exc.UnrecognizedPropertyException: Unrecognized field "overriddenStatus" (class com.netflix.appinfo.InstanceInfo), not marked as ignorable (28 known properties: "port", "healthCheckUrl", "appGroupName", "sid", "instanceId", "countryId", "hostName", "isCoordinatingDiscoveryServer", "vipAddress", "securePort", "secureHealthCheckUrl", "overridden_status", "asgName", "app", "overriddenstatus", "leaseInfo", "dataCenterInfo", "secureVipAddress", "metadata", "status", "ipAddr", "is_dirty", "homePageUrl", "statusPageUrl", "lastUpdatedTimestamp", "lastDirtyTimestamp", "actionType", "status_without_dirty"])
 at [Source: (PushbackInputStream); line: 1, column: 1067] (through reference chain: com.netflix.discovery.converters.jackson.builder.ApplicationsJacksonBuilder["application"]->java.util.ArrayList[0]->com.netflix.discovery.shared.Application["instance"]->java.util.ArrayList[0]->com.netflix.appinfo.InstanceInfo["overriddenStatus"])
	at org.springframework.web.client.HttpMessageConverterExtractor.extractData(HttpMessageConverterExtractor.java:115) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.web.client.RestTemplate$ResponseEntityResponseExtractor.extractData(RestTemplate.java:1008) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.web.client.RestTemplate$ResponseEntityResponseExtractor.extractData(RestTemplate.java:991) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.web.client.RestTemplate.doExecute(RestTemplate.java:732) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.web.client.RestTemplate.execute(RestTemplate.java:686) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.web.client.RestTemplate.exchange(RestTemplate.java:602) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.cloud.netflix.eureka.http.RestTemplateEurekaHttpClient.getApplicationsInternal(RestTemplateEurekaHttpClient.java:148) ~[spring-cloud-netflix-eureka-client-2.0.0.M8.jar:2.0.0.M8]
	at org.springframework.cloud.netflix.eureka.http.RestTemplateEurekaHttpClient.getApplications(RestTemplateEurekaHttpClient.java:137) ~[spring-cloud-netflix-eureka-client-2.0.0.M8.jar:2.0.0.M8]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator$6.execute(EurekaHttpClientDecorator.java:137) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.RedirectingEurekaHttpClient.execute(RedirectingEurekaHttpClient.java:89) ~[eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator.getApplications(EurekaHttpClientDecorator.java:134) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator$6.execute(EurekaHttpClientDecorator.java:137) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.RetryableEurekaHttpClient.execute(RetryableEurekaHttpClient.java:120) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator.getApplications(EurekaHttpClientDecorator.java:134) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator$6.execute(EurekaHttpClientDecorator.java:137) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.SessionedEurekaHttpClient.execute(SessionedEurekaHttpClient.java:77) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator.getApplications(EurekaHttpClientDecorator.java:134) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.DiscoveryClient.getAndStoreFullRegistry(DiscoveryClient.java:1051) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.DiscoveryClient.fetchRegistry(DiscoveryClient.java:965) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.DiscoveryClient.refreshRegistry(DiscoveryClient.java:1471) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.DiscoveryClient$CacheRefreshThread.run(DiscoveryClient.java:1438) [eureka-client-1.8.7.jar:1.8.7]
	at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511) [na:1.8.0_162]
	at java.util.concurrent.FutureTask.run(FutureTask.java:266) [na:1.8.0_162]
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149) [na:1.8.0_162]
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624) [na:1.8.0_162]
	at java.lang.Thread.run(Thread.java:748) [na:1.8.0_162]
Caused by: org.springframework.http.converter.HttpMessageNotReadableException: JSON parse error: Unrecognized field "overriddenStatus" (class com.netflix.appinfo.InstanceInfo), not marked as ignorable; nested exception is com.fasterxml.jackson.databind.exc.UnrecognizedPropertyException: Unrecognized field "overriddenStatus" (class com.netflix.appinfo.InstanceInfo), not marked as ignorable (28 known properties: "port", "healthCheckUrl", "appGroupName", "sid", "instanceId", "countryId", "hostName", "isCoordinatingDiscoveryServer", "vipAddress", "securePort", "secureHealthCheckUrl", "overridden_status", "asgName", "app", "overriddenstatus", "leaseInfo", "dataCenterInfo", "secureVipAddress", "metadata", "status", "ipAddr", "is_dirty", "homePageUrl", "statusPageUrl", "lastUpdatedTimestamp", "lastDirtyTimestamp", "actionType", "status_without_dirty"])
 at [Source: (PushbackInputStream); line: 1, column: 1067] (through reference chain: com.netflix.discovery.converters.jackson.builder.ApplicationsJacksonBuilder["application"]->java.util.ArrayList[0]->com.netflix.discovery.shared.Application["instance"]->java.util.ArrayList[0]->com.netflix.appinfo.InstanceInfo["overriddenStatus"])
	at org.springframework.http.converter.json.AbstractJackson2HttpMessageConverter.readJavaType(AbstractJackson2HttpMessageConverter.java:241) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.http.converter.json.AbstractJackson2HttpMessageConverter.read(AbstractJackson2HttpMessageConverter.java:223) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.web.client.HttpMessageConverterExtractor.extractData(HttpMessageConverterExtractor.java:100) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	... 25 common frames omitted
Caused by: com.fasterxml.jackson.databind.exc.UnrecognizedPropertyException: Unrecognized field "overriddenStatus" (class com.netflix.appinfo.InstanceInfo), not marked as ignorable (28 known properties: "port", "healthCheckUrl", "appGroupName", "sid", "instanceId", "countryId", "hostName", "isCoordinatingDiscoveryServer", "vipAddress", "securePort", "secureHealthCheckUrl", "overridden_status", "asgName", "app", "overriddenstatus", "leaseInfo", "dataCenterInfo", "secureVipAddress", "metadata", "status", "ipAddr", "is_dirty", "homePageUrl", "statusPageUrl", "lastUpdatedTimestamp", "lastDirtyTimestamp", "actionType", "status_without_dirty"])
 at [Source: (PushbackInputStream); line: 1, column: 1067] (through reference chain: com.netflix.discovery.converters.jackson.builder.ApplicationsJacksonBuilder["application"]->java.util.ArrayList[0]->com.netflix.discovery.shared.Application["instance"]->java.util.ArrayList[0]->com.netflix.appinfo.InstanceInfo["overriddenStatus"])
	at com.fasterxml.jackson.databind.exc.UnrecognizedPropertyException.from(UnrecognizedPropertyException.java:60) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.DeserializationContext.handleUnknownProperty(DeserializationContext.java:822) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.std.StdDeserializer.handleUnknownProperty(StdDeserializer.java:1152) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializerBase.handleUnknownProperty(BeanDeserializerBase.java:1567) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializerBase.handleUnknownProperties(BeanDeserializerBase.java:1521) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializer._deserializeUsingPropertyBased(BeanDeserializer.java:503) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializerBase.deserializeFromObjectUsingNonDefault(BeanDeserializerBase.java:1265) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializer.deserializeFromObject(BeanDeserializer.java:325) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializer.deserialize(BeanDeserializer.java:159) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.std.CollectionDeserializer.deserialize(CollectionDeserializer.java:285) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.std.CollectionDeserializer.deserialize(CollectionDeserializer.java:244) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.std.CollectionDeserializer.deserialize(CollectionDeserializer.java:27) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.SettableBeanProperty.deserialize(SettableBeanProperty.java:519) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializer._deserializeWithErrorWrapping(BeanDeserializer.java:527) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializer._deserializeUsingPropertyBased(BeanDeserializer.java:416) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializerBase.deserializeFromObjectUsingNonDefault(BeanDeserializerBase.java:1265) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializer.deserializeFromObject(BeanDeserializer.java:325) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializer.deserialize(BeanDeserializer.java:159) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.std.CollectionDeserializer.deserialize(CollectionDeserializer.java:285) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.std.CollectionDeserializer.deserialize(CollectionDeserializer.java:244) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.std.CollectionDeserializer.deserialize(CollectionDeserializer.java:27) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.impl.MethodProperty.deserializeSetAndReturn(MethodProperty.java:149) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BuilderBasedDeserializer.vanillaDeserialize(BuilderBasedDeserializer.java:269) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BuilderBasedDeserializer.deserialize(BuilderBasedDeserializer.java:193) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.ObjectMapper._unwrapAndDeserialize(ObjectMapper.java:4081) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.ObjectMapper._readMapAndClose(ObjectMapper.java:3999) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.ObjectMapper.readValue(ObjectMapper.java:3072) ~[jackson-databind-2.9.3.jar:2.9.3]
	at org.springframework.http.converter.json.AbstractJackson2HttpMessageConverter.readJavaType(AbstractJackson2HttpMessageConverter.java:235) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	... 27 common frames omitted

2018-04-05 17:57:58.483  WARN 7576 --- [freshExecutor-0] c.n.d.s.t.d.RetryableEurekaHttpClient    : Request execution failed with message: Error while extracting response for type [class org.springframework.cloud.netflix.eureka.http.EurekaApplications] and content type [application/json]; nested exception is org.springframework.http.converter.HttpMessageNotReadableException: JSON parse error: Unrecognized field "overriddenStatus" (class com.netflix.appinfo.InstanceInfo), not marked as ignorable; nested exception is com.fasterxml.jackson.databind.exc.UnrecognizedPropertyException: Unrecognized field "overriddenStatus" (class com.netflix.appinfo.InstanceInfo), not marked as ignorable (28 known properties: "port", "healthCheckUrl", "appGroupName", "sid", "instanceId", "countryId", "hostName", "isCoordinatingDiscoveryServer", "vipAddress", "securePort", "secureHealthCheckUrl", "overridden_status", "asgName", "app", "overriddenstatus", "leaseInfo", "dataCenterInfo", "secureVipAddress", "metadata", "status", "ipAddr", "is_dirty", "homePageUrl", "statusPageUrl", "lastUpdatedTimestamp", "lastDirtyTimestamp", "actionType", "status_without_dirty"])
 at [Source: (PushbackInputStream); line: 1, column: 1067] (through reference chain: com.netflix.discovery.converters.jackson.builder.ApplicationsJacksonBuilder["application"]->java.util.ArrayList[0]->com.netflix.discovery.shared.Application["instance"]->java.util.ArrayList[0]->com.netflix.appinfo.InstanceInfo["overriddenStatus"])
2018-04-05 17:57:58.509 ERROR 7576 --- [freshExecutor-0] c.n.d.s.t.d.RedirectingEurekaHttpClient  : Request execution error

org.springframework.web.client.RestClientException: Error while extracting response for type [class org.springframework.cloud.netflix.eureka.http.EurekaApplications] and content type [application/json]; nested exception is org.springframework.http.converter.HttpMessageNotReadableException: JSON parse error: Unrecognized field "overriddenStatus" (class com.netflix.appinfo.InstanceInfo), not marked as ignorable; nested exception is com.fasterxml.jackson.databind.exc.UnrecognizedPropertyException: Unrecognized field "overriddenStatus" (class com.netflix.appinfo.InstanceInfo), not marked as ignorable (28 known properties: "port", "healthCheckUrl", "appGroupName", "sid", "instanceId", "countryId", "hostName", "isCoordinatingDiscoveryServer", "vipAddress", "securePort", "secureHealthCheckUrl", "overridden_status", "asgName", "app", "overriddenstatus", "leaseInfo", "dataCenterInfo", "secureVipAddress", "metadata", "status", "ipAddr", "is_dirty", "homePageUrl", "statusPageUrl", "lastUpdatedTimestamp", "lastDirtyTimestamp", "actionType", "status_without_dirty"])
 at [Source: (PushbackInputStream); line: 1, column: 1067] (through reference chain: com.netflix.discovery.converters.jackson.builder.ApplicationsJacksonBuilder["application"]->java.util.ArrayList[0]->com.netflix.discovery.shared.Application["instance"]->java.util.ArrayList[0]->com.netflix.appinfo.InstanceInfo["overriddenStatus"])
	at org.springframework.web.client.HttpMessageConverterExtractor.extractData(HttpMessageConverterExtractor.java:115) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.web.client.RestTemplate$ResponseEntityResponseExtractor.extractData(RestTemplate.java:1008) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.web.client.RestTemplate$ResponseEntityResponseExtractor.extractData(RestTemplate.java:991) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.web.client.RestTemplate.doExecute(RestTemplate.java:732) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.web.client.RestTemplate.execute(RestTemplate.java:686) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.web.client.RestTemplate.exchange(RestTemplate.java:602) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.cloud.netflix.eureka.http.RestTemplateEurekaHttpClient.getApplicationsInternal(RestTemplateEurekaHttpClient.java:148) ~[spring-cloud-netflix-eureka-client-2.0.0.M8.jar:2.0.0.M8]
	at org.springframework.cloud.netflix.eureka.http.RestTemplateEurekaHttpClient.getApplications(RestTemplateEurekaHttpClient.java:137) ~[spring-cloud-netflix-eureka-client-2.0.0.M8.jar:2.0.0.M8]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator$6.execute(EurekaHttpClientDecorator.java:137) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.RedirectingEurekaHttpClient.executeOnNewServer(RedirectingEurekaHttpClient.java:118) ~[eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.RedirectingEurekaHttpClient.execute(RedirectingEurekaHttpClient.java:79) ~[eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator.getApplications(EurekaHttpClientDecorator.java:134) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator$6.execute(EurekaHttpClientDecorator.java:137) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.RetryableEurekaHttpClient.execute(RetryableEurekaHttpClient.java:120) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator.getApplications(EurekaHttpClientDecorator.java:134) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator$6.execute(EurekaHttpClientDecorator.java:137) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.SessionedEurekaHttpClient.execute(SessionedEurekaHttpClient.java:77) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator.getApplications(EurekaHttpClientDecorator.java:134) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.DiscoveryClient.getAndStoreFullRegistry(DiscoveryClient.java:1051) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.DiscoveryClient.fetchRegistry(DiscoveryClient.java:965) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.DiscoveryClient.refreshRegistry(DiscoveryClient.java:1471) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.DiscoveryClient$CacheRefreshThread.run(DiscoveryClient.java:1438) [eureka-client-1.8.7.jar:1.8.7]
	at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511) [na:1.8.0_162]
	at java.util.concurrent.FutureTask.run(FutureTask.java:266) [na:1.8.0_162]
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149) [na:1.8.0_162]
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624) [na:1.8.0_162]
	at java.lang.Thread.run(Thread.java:748) [na:1.8.0_162]
Caused by: org.springframework.http.converter.HttpMessageNotReadableException: JSON parse error: Unrecognized field "overriddenStatus" (class com.netflix.appinfo.InstanceInfo), not marked as ignorable; nested exception is com.fasterxml.jackson.databind.exc.UnrecognizedPropertyException: Unrecognized field "overriddenStatus" (class com.netflix.appinfo.InstanceInfo), not marked as ignorable (28 known properties: "port", "healthCheckUrl", "appGroupName", "sid", "instanceId", "countryId", "hostName", "isCoordinatingDiscoveryServer", "vipAddress", "securePort", "secureHealthCheckUrl", "overridden_status", "asgName", "app", "overriddenstatus", "leaseInfo", "dataCenterInfo", "secureVipAddress", "metadata", "status", "ipAddr", "is_dirty", "homePageUrl", "statusPageUrl", "lastUpdatedTimestamp", "lastDirtyTimestamp", "actionType", "status_without_dirty"])
 at [Source: (PushbackInputStream); line: 1, column: 1067] (through reference chain: com.netflix.discovery.converters.jackson.builder.ApplicationsJacksonBuilder["application"]->java.util.ArrayList[0]->com.netflix.discovery.shared.Application["instance"]->java.util.ArrayList[0]->com.netflix.appinfo.InstanceInfo["overriddenStatus"])
	at org.springframework.http.converter.json.AbstractJackson2HttpMessageConverter.readJavaType(AbstractJackson2HttpMessageConverter.java:241) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.http.converter.json.AbstractJackson2HttpMessageConverter.read(AbstractJackson2HttpMessageConverter.java:223) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	at org.springframework.web.client.HttpMessageConverterExtractor.extractData(HttpMessageConverterExtractor.java:100) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	... 26 common frames omitted
Caused by: com.fasterxml.jackson.databind.exc.UnrecognizedPropertyException: Unrecognized field "overriddenStatus" (class com.netflix.appinfo.InstanceInfo), not marked as ignorable (28 known properties: "port", "healthCheckUrl", "appGroupName", "sid", "instanceId", "countryId", "hostName", "isCoordinatingDiscoveryServer", "vipAddress", "securePort", "secureHealthCheckUrl", "overridden_status", "asgName", "app", "overriddenstatus", "leaseInfo", "dataCenterInfo", "secureVipAddress", "metadata", "status", "ipAddr", "is_dirty", "homePageUrl", "statusPageUrl", "lastUpdatedTimestamp", "lastDirtyTimestamp", "actionType", "status_without_dirty"])
 at [Source: (PushbackInputStream); line: 1, column: 1067] (through reference chain: com.netflix.discovery.converters.jackson.builder.ApplicationsJacksonBuilder["application"]->java.util.ArrayList[0]->com.netflix.discovery.shared.Application["instance"]->java.util.ArrayList[0]->com.netflix.appinfo.InstanceInfo["overriddenStatus"])
	at com.fasterxml.jackson.databind.exc.UnrecognizedPropertyException.from(UnrecognizedPropertyException.java:60) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.DeserializationContext.handleUnknownProperty(DeserializationContext.java:822) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.std.StdDeserializer.handleUnknownProperty(StdDeserializer.java:1152) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializerBase.handleUnknownProperty(BeanDeserializerBase.java:1567) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializerBase.handleUnknownProperties(BeanDeserializerBase.java:1521) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializer._deserializeUsingPropertyBased(BeanDeserializer.java:503) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializerBase.deserializeFromObjectUsingNonDefault(BeanDeserializerBase.java:1265) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializer.deserializeFromObject(BeanDeserializer.java:325) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializer.deserialize(BeanDeserializer.java:159) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.std.CollectionDeserializer.deserialize(CollectionDeserializer.java:285) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.std.CollectionDeserializer.deserialize(CollectionDeserializer.java:244) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.std.CollectionDeserializer.deserialize(CollectionDeserializer.java:27) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.SettableBeanProperty.deserialize(SettableBeanProperty.java:519) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializer._deserializeWithErrorWrapping(BeanDeserializer.java:527) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializer._deserializeUsingPropertyBased(BeanDeserializer.java:416) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializerBase.deserializeFromObjectUsingNonDefault(BeanDeserializerBase.java:1265) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializer.deserializeFromObject(BeanDeserializer.java:325) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BeanDeserializer.deserialize(BeanDeserializer.java:159) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.std.CollectionDeserializer.deserialize(CollectionDeserializer.java:285) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.std.CollectionDeserializer.deserialize(CollectionDeserializer.java:244) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.std.CollectionDeserializer.deserialize(CollectionDeserializer.java:27) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.impl.MethodProperty.deserializeSetAndReturn(MethodProperty.java:149) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BuilderBasedDeserializer.vanillaDeserialize(BuilderBasedDeserializer.java:269) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.deser.BuilderBasedDeserializer.deserialize(BuilderBasedDeserializer.java:193) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.ObjectMapper._unwrapAndDeserialize(ObjectMapper.java:4081) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.ObjectMapper._readMapAndClose(ObjectMapper.java:3999) ~[jackson-databind-2.9.3.jar:2.9.3]
	at com.fasterxml.jackson.databind.ObjectMapper.readValue(ObjectMapper.java:3072) ~[jackson-databind-2.9.3.jar:2.9.3]
	at org.springframework.http.converter.json.AbstractJackson2HttpMessageConverter.readJavaType(AbstractJackson2HttpMessageConverter.java:235) ~[spring-web-5.0.4.RELEASE.jar:5.0.4.RELEASE]
	... 28 common frames omitted

2018-04-05 17:57:58.511  WARN 7576 --- [freshExecutor-0] c.n.d.s.t.d.RetryableEurekaHttpClient    : Request execution failed with message: Error while extracting response for type [class org.springframework.cloud.netflix.eureka.http.EurekaApplications] and content type [application/json]; nested exception is org.springframework.http.converter.HttpMessageNotReadableException: JSON parse error: Unrecognized field "overriddenStatus" (class com.netflix.appinfo.InstanceInfo), not marked as ignorable; nested exception is com.fasterxml.jackson.databind.exc.UnrecognizedPropertyException: Unrecognized field "overriddenStatus" (class com.netflix.appinfo.InstanceInfo), not marked as ignorable (28 known properties: "port", "healthCheckUrl", "appGroupName", "sid", "instanceId", "countryId", "hostName", "isCoordinatingDiscoveryServer", "vipAddress", "securePort", "secureHealthCheckUrl", "overridden_status", "asgName", "app", "overriddenstatus", "leaseInfo", "dataCenterInfo", "secureVipAddress", "metadata", "status", "ipAddr", "is_dirty", "homePageUrl", "statusPageUrl", "lastUpdatedTimestamp", "lastDirtyTimestamp", "actionType", "status_without_dirty"])
 at [Source: (PushbackInputStream); line: 1, column: 1067] (through reference chain: com.netflix.discovery.converters.jackson.builder.ApplicationsJacksonBuilder["application"]->java.util.ArrayList[0]->com.netflix.discovery.shared.Application["instance"]->java.util.ArrayList[0]->com.netflix.appinfo.InstanceInfo["overriddenStatus"])
2018-04-05 17:57:58.514 ERROR 7576 --- [freshExecutor-0] com.netflix.discovery.DiscoveryClient    : DiscoveryClient_HELLO-SERVICE/localhost:hello-service:8080 - was unable to refresh its cache! status = Cannot execute request on any known server

com.netflix.discovery.shared.transport.TransportException: Cannot execute request on any known server
	at com.netflix.discovery.shared.transport.decorator.RetryableEurekaHttpClient.execute(RetryableEurekaHttpClient.java:112) ~[eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator.getApplications(EurekaHttpClientDecorator.java:134) ~[eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator$6.execute(EurekaHttpClientDecorator.java:137) ~[eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.SessionedEurekaHttpClient.execute(SessionedEurekaHttpClient.java:77) ~[eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.shared.transport.decorator.EurekaHttpClientDecorator.getApplications(EurekaHttpClientDecorator.java:134) ~[eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.DiscoveryClient.getAndStoreFullRegistry(DiscoveryClient.java:1051) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.DiscoveryClient.fetchRegistry(DiscoveryClient.java:965) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.DiscoveryClient.refreshRegistry(DiscoveryClient.java:1471) [eureka-client-1.8.7.jar:1.8.7]
	at com.netflix.discovery.DiscoveryClient$CacheRefreshThread.run(DiscoveryClient.java:1438) [eureka-client-1.8.7.jar:1.8.7]
	at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511) [na:1.8.0_162]
	at java.util.concurrent.FutureTask.run(FutureTask.java:266) [na:1.8.0_162]
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149) [na:1.8.0_162]
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624) [na:1.8.0_162]
	at java.lang.Thread.run(Thread.java:748) [na:1.8.0_162]

```

