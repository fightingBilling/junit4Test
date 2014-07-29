### maven + Junit4 examples
# 项目介绍
  本项目使用Junit进行功能单元测试，并测试maven插件的使用
  在默认情况下，maven执行test功能测试后，对main下的程序进行功能打包，但是不会对test下的测试程序进行打包
  
# Maven下test打包
You can produce a jar which will include your test classes and resources.

<project>
  ...
  <build>
    <plugins>
      ...
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-jar-plugin</artifactId>
        <version>2.5</version>
        <executions>
          <execution>
            <goals>
              <goal>test-jar</goal>
            </goals>
          </execution>
        </executions>
      </plugin>
      ...
    </plugins>
  </build>
  ...
</project>

To reuse this artifact in an other project, you must declare this dependency with type test-jar :

<project>
  ...
  <dependencies>
    <dependency>
      <groupId>groupId</groupId>
      <artifactId>artifactId</artifactId>
      <type>test-jar</type>
      <version>version</version>
      <scope>test</scope>
    </dependency>
  </dependencies>
  ...
</project>