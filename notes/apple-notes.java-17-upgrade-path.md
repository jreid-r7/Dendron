---
id: i128sd06t7mngms5f7196dg
title: Java 17 Upgrade Path
desc: ''
updated: 1723636850021
created: 1723636850021
isDir: false
---
1. Mockito - may need to go to at least 4
2. Mockito Unit Jupiter - at least 4
3. Lombok 1.18.26


<dependency>
    <groupId>org.mockito</groupId>
    <artifactId>mockito-junit-jupiter</artifactId>
    <version>4.11.0</version>
</dependency>
<dependency>
    <groupId>net.bytebuddy</groupId>
    <artifactId>byte-buddy</artifactId>
    <version>1.12.19</version>
</dependency>
<dependency>
    <groupId>net.bytebuddy</groupId>
    <artifactId>byte-buddy-agent</artifactId>
    <version>1.12.19</version>
</dependency>
<dependency>
    <groupId>org.objenesis</groupId>
    <artifactId>objenesis</artifactId>
    <version>3.3</version>
</dependency>