---
title: Integrate McNative licensing
---

## Introduction

McNative Hybrid Plugins are plugins that are built on a different platform like Bukkit or BungeeCord, but 
are fully integrated into the McNative environment. 

## Pre Requirement

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

## Get Started 



### Setup the licensing framework

The setup of the framework is very simple and requires only a few code lines. 

@Todo write

| Plugin Framework | Class                                                 |
| -------------    |:-------------:
| McNative         | `org.mcnative.licensing.platform.McNativeIntegration` |
| Bukkit           | `org.mcnative.licensing.platform.BukkitIntegration`   |
| BungeeCord       | `org.mcnative.licensing.platform.BungeeIntegration`   |

In this example setup with use the McNative plugin framework.

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


### Setup the McNative Premium reporting service 
```java
McNativeIntegration.startReportingService(this,RESOURCE_ID);
```
