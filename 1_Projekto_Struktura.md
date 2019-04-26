# Projekto struktūra

Sukuriame projektą naudojant https://start.spring.io/ .

Parinkus parametrus:
* Project Gradle
* Language Java
* Spring Boot 2.1.4
* group, artifact - savo nuožiūra
* Dependencies: Web, DevTools, Cache, JPA
Pasirenkame mygtuką `Generate`. Turėtume gauti sugeneruotą projektą zip faile.

Išskleidžiamas failas patogioje vietoje.

Importuojame projektą į intellij.

Importavus, Gradle build sistema fone parsiųs `Spring framework`

Pridedame duomenų bazės parametrus į `src/main/resources/application.properties` failą:

```
spring.datasource.driver-class-name=org.h2.Driver
spring.datasource.url=jdbc:h2:mem:localhost
spring.datasource.username=admin
spring.datasource.password=
```

pridedame duomenų bazės biblioteką:

į failą `build.gradle` `depdendencies` fragmente pridedame
```
implementation 'com.h2database:h2'
```

Gradle meniu atnaujiname bibliotekas

Paleidžiame aplikaciją:
atsidarius `src/main/java/com.example.demo/DemoApplication.java` ant `main` metodo spaudžiame dešiniu klavišu, pasirenkame "Run application"

Viskam pavykus sėkmingai aplikacijos loguose matysime sėkmingo paleidimo logus
```
  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v2.1.4.RELEASE)

2019-04-26 19:22:07.938  INFO 22037 --- [  restartedMain] com.example.demo.DemoApplication         : Starting DemoApplication on andrius-ThinkPad-E480 with PID 22037 (/home/andrius/workspace/demo/out/production/classes started by andrius in /home/andrius/workspace/demo)
2019-04-26 19:22:07.942  INFO 22037 --- [  restartedMain] com.example.demo.DemoApplication         : No active profile set, falling back to default profiles: default
2019-04-26 19:22:07.976  INFO 22037 --- [  restartedMain] .e.DevToolsPropertyDefaultsPostProcessor : Devtools property defaults active! Set 'spring.devtools.add-properties' to 'false' to disable
2019-04-26 19:22:07.976  INFO 22037 --- [  restartedMain] .e.DevToolsPropertyDefaultsPostProcessor : For additional web related logging consider setting the 'logging.level.web' property to 'DEBUG'
2019-04-26 19:22:08.653  INFO 22037 --- [  restartedMain] .s.d.r.c.RepositoryConfigurationDelegate : Bootstrapping Spring Data repositories in DEFAULT mode.
2019-04-26 19:22:08.671  INFO 22037 --- [  restartedMain] .s.d.r.c.RepositoryConfigurationDelegate : Finished Spring Data repository scanning in 12ms. Found 0 repository interfaces.
2019-04-26 19:22:08.980  INFO 22037 --- [  restartedMain] trationDelegate$BeanPostProcessorChecker : Bean 'org.springframework.transaction.annotation.ProxyTransactionManagementConfiguration' of type [org.springframework.transaction.annotation.ProxyTransactionManagementConfiguration$$EnhancerBySpringCGLIB$$7e3a83e6] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2019-04-26 19:22:09.306  INFO 22037 --- [  restartedMain] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2019-04-26 19:22:09.324  INFO 22037 --- [  restartedMain] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2019-04-26 19:22:09.324  INFO 22037 --- [  restartedMain] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.17]
2019-04-26 19:22:09.395  INFO 22037 --- [  restartedMain] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2019-04-26 19:22:09.396  INFO 22037 --- [  restartedMain] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 1420 ms
2019-04-26 19:22:09.513  INFO 22037 --- [  restartedMain] com.zaxxer.hikari.HikariDataSource       : HikariPool-1 - Starting...
2019-04-26 19:22:09.583  INFO 22037 --- [  restartedMain] com.zaxxer.hikari.HikariDataSource       : HikariPool-1 - Start completed.
2019-04-26 19:22:09.668  INFO 22037 --- [  restartedMain] o.hibernate.jpa.internal.util.LogHelper  : HHH000204: Processing PersistenceUnitInfo [
	name: default
	...]
2019-04-26 19:22:09.706  INFO 22037 --- [  restartedMain] org.hibernate.Version                    : HHH000412: Hibernate Core {5.3.9.Final}
2019-04-26 19:22:09.706  INFO 22037 --- [  restartedMain] org.hibernate.cfg.Environment            : HHH000206: hibernate.properties not found
2019-04-26 19:22:09.801  INFO 22037 --- [  restartedMain] o.hibernate.annotations.common.Version   : HCANN000001: Hibernate Commons Annotations {5.0.4.Final}
2019-04-26 19:22:09.877  INFO 22037 --- [  restartedMain] org.hibernate.dialect.Dialect            : HHH000400: Using dialect: org.hibernate.dialect.H2Dialect
2019-04-26 19:22:10.003  INFO 22037 --- [  restartedMain] o.h.t.schema.internal.SchemaCreatorImpl  : HHH000476: Executing import script 'org.hibernate.tool.schema.internal.exec.ScriptSourceInputNonExistentImpl@249aa3f0'
2019-04-26 19:22:10.005  INFO 22037 --- [  restartedMain] j.LocalContainerEntityManagerFactoryBean : Initialized JPA EntityManagerFactory for persistence unit 'default'
2019-04-26 19:22:10.040  INFO 22037 --- [  restartedMain] o.s.b.d.a.OptionalLiveReloadServer       : LiveReload server is running on port 35729
2019-04-26 19:22:10.188  INFO 22037 --- [  restartedMain] o.s.s.concurrent.ThreadPoolTaskExecutor  : Initializing ExecutorService 'applicationTaskExecutor'
2019-04-26 19:22:10.215  WARN 22037 --- [  restartedMain] aWebConfiguration$JpaWebMvcConfiguration : spring.jpa.open-in-view is enabled by default. Therefore, database queries may be performed during view rendering. Explicitly configure spring.jpa.open-in-view to disable this warning
2019-04-26 19:22:10.370  INFO 22037 --- [  restartedMain] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2019-04-26 19:22:10.373  INFO 22037 --- [  restartedMain] com.example.demo.DemoApplication         : Started DemoApplication in 2.706 seconds (JVM running for 3.233)
```