---
title: Integrate McNative licensing
---

# Introduction



# Pre Requirement

**For Maven**
```xml
<repository>
    <id>pretronic</id>
    <url>https://repository.pretronic.net/repository/pretronic/</url>
</repository>

<dependency>
    <groupId>org.mcnative</groupId>
    <artifactId>mcnative-licensing</artifactId>
    <version>${mcnative.version}</version>
    <scope>compile</scope>
</dependency>
```

**For Gradle**

# Get Started 



## Setup the licensing framework

The setup of the framework is very simple and requires only a few code lines. 

@Todo write

| Plugin Framework | Class                                                 |
| -------------    |:-------------:
| McNative         | `org.mcnative.licensing.platform.McNativeIntegration` |
| Bukkit           | `org.mcnative.licensing.platform.BukkitIntegration`   |
| BungeeCord       | `org.mcnative.licensing.platform.BungeeIntegration`   |

In this example setup we use the McNative plugin framework.

```java
public static String RESOURCE_ID ="440a71ff-01ea-43f7-a483-f46940f24d29";
public static String PUBLIC_KEY = "MIIBIjANBg.....AQAB";
```

```java
try{
    McNativeIntegration.verifyOrCheckout(this,RESOURCE_ID,PUBLIC_KEY);
}catch (LicenseNotValidException | CloudNotCheckoutLicenseException e){
    getLogger().error("--------------------------------");
    getLogger().error("-> Invalid license");
    getLogger().error("-> Error: "+e.getMessage());
    getLogger().error("--------------------------------");
    getLogger().info("Plugin is shutting down");
    getLoader().shutdown();
    return;
}
```


## Setup the McNative Premium reporting service 
```java
McNativeIntegration.startReportingService(this,RESOURCE_ID);
```

=== "C"

    ``` c
    #include <stdio.h>

    int main(void) {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` c++
    #include <iostream>

    int main(void) {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```
