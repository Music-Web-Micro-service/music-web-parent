# music-web-parent
## Prepareing
Authenticating to GitHub Packages from Maven
enable Authenticating info in your ~/.m2/settings.xml file. Remember to replace the **UserName** and **Token**. **UserName** is Your Acoount UserName, And **Token** is in Settings of your Account -> developer settings -> token classic -> generate
```yaml
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                      http://maven.apache.org/xsd/settings-1.0.0.xsd">

  <activeProfiles>
    <activeProfile>github</activeProfile>
  </activeProfiles>

  <profiles>
    <profile>
      <id>github</id>
      <repositories>
        <repository>
          <id>central</id>
          <url>https://repo1.maven.org/maven2</url>
        </repository>
        <repository>
          <id>github</id>
          <url>https://maven.pkg.github.com/OWNER/REPOSITORY</url>
          <snapshots>
            <enabled>true</enabled>
          </snapshots>
        </repository>
      </repositories>
    </profile>
  </profiles>

  <servers>
    <server>
      <id>github</id>
      <username>USERNAME</username>
      <password>TOKEN</password>
    </server>
  </servers>
</settings>
```
Check the Packages in oganization page. And click the **com.freemusic.music-web-Parent** and Follow the instruction

Add the package dependencies to the dependencies element of your project pom.xml file, replacing com.example:test with your package.
```yaml
<dependencies>
 <dependency>
    <groupId>com.example</groupId>
    <artifactId>test</artifactId>
    <version>1.0.0-SNAPSHOT</version>
  </dependency>
</dependencies>
```
Install the package.

`mvn install`
