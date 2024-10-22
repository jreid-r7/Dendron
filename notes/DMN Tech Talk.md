---
id: k1d4hx7jx70fp0kxrbsuivr
title: DMN Tech Talk
desc: ''
updated: 1729167461574
created: 1729150152934
---

```mvn archetype:generate -B -DarchetypeGroupId=org.kie.kogito -DarchetypeArtifactId=kogito-spring-boot-archetype -DarchetypeVersion=1.44.1.Final -DgroupId=com.rapid7.platform.ipims -DartifactId=test-dmn -Dversion=0.0.1-SNAPSHOT -Dpackage=com.rapid7.platform.ipims```

```xml
    <dependency>
      <groupId>org.kie.kogito</groupId>
      <artifactId>kogito-scenario-simulation</artifactId>
      <scope>test</scope>
    </dependency>
```

```KogitoScenarioJUnitActivatorTest.java```

```java
package testscenarios;
@org.junit.runner.RunWith(org.kogito.scenariosimulation.runner.KogitoJunitActivator.class)
public class KogitoScenarioJUnitActivatorTest {
}
```

Language Support for Java by RedHat