# 常见问题处理

- Q:执行Maven install或Maven test命令时控制台输出乱码的解决办法

  A:  在Maven的pom.xml文件中增加

  ~~~xml
  <!-- 方案一 -->
  <properties> <argLine>-Dfile.encoding=UTF-8</argLine> </properties>
  <!-- 方案二 -->
  <build>
    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-surefire-plugin</artifactId>
        <version>2.16</version>
        <configuration>
          <forkMode>once</forkMode>
          <argLine>-Dfile.encoding=UTF-8</argLine>
        </configuration>
      </plugin>
    </plugins>
  </build>
  ~~~

- 