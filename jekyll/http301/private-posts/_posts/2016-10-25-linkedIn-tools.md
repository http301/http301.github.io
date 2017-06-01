---
title: LinkedIn Tools
date: 2016-10-25 16:32:28
tags:
---

* TOC
{:toc}

## [Offspring](https://iwww.corp.linkedin.com/wiki/cf/display/ENGS/Offspring+Overview)

### What is Offspring?

Offspring is a framework for **creating, configuring, and composing components** at LinkedIn.

- Offspring is an alternative to dependency injection mechanisms like Spring and LinkedIn's LiSpring that addresses common problems with these frameworks.
- Unlike Spring/LiSpring, Offspring is not a dependency injection framework. It's an alternative to dependency injection mechanisms like Spring and LinkedIn's LiSpring.
- Offspring allows you to obtain objects from a factory explicitly in your code.

### Basic Concepts

#### Factories

A configurable template used to create an object. All Offspring objects are instantiated via a factory. The factory loads configurations, creates any dependent objects, and finally creates and returns an object. Unlike typical java Factory design patterns, Offspring Factories are not invoked directly, **they are called indirectly from other Factories or BootListeners**.

#### BootListeners

A BootListener provides a way to integrate with Servlet Containers. A BootListener **provides a hook for you to instantiate required objects for your application when the servlet context gets initialized**. This is useful for objects that should not be initialized or created until your service is initialized and ready to run.

#### Generator and Object Life-Cycles

**Generator is the core of Offspring**, but is typically not used directly. It is responsible for actually **creating the objects using the Offspring factories**. Creation is done in an on-demand manner (**lazy initialization**). Generator is also responsible for **managing the life cycles of the objects**. Typically there is no need to interact directly with generator, except in BootListeners. **OffSpring objects have a life-cycle that consists of initialization, starting, running, stopping, and shutdown**.

#### Config 2 Integration

**Offspring uses Config2 to inject the configurable properties**. The app-def for config2 would be generated based on the Offspring factories used; and Offspring would use compiled config2 properties when instantiating objects.

#### Scopes

**A scope is a unique identifier for an object or a configuration**. Offspring uses scopes to manage both configurations and objects. While scopes are often hierarchical in structure, you can imagine that Offspring maintains a mapping from scopes to configurations and objects. A common place to encounter scopes is in in Config2 property files. For example, you might see a property entry like *<property name="server.db.connnectionString" property="localhost:1234" />*. This is an example of value (known as a configuration key)  being set within nested scopes, "server" and "db".

---

## [Configuration 2.0](https://iwww.corp.linkedin.com/wiki/cf/display/TOOLS/Configuration+2.0)

### How does Config 2.0 work?

- The product(service) tells config 2.0 that there is a set of properties that needs to be defined for the product(service) to start running. This information is given through a file called *AppDef*.
- These values can come from several locations: **default values provided along with the AppDef file**, or values **from the config source**.
- All these values are **compiled and published** so that they can be consumed during deployment.

#### The cfg2 compiler uses the following rules to resolve properties:

- Resolve the property from config sources.
- If nothing is found, use the default value provided by the app-def.
- If no default value is found, display an error.

![cfg2_tutorial.png](../assets/cfg2_tutorial.png)

### Benefits

- Through this process, **developers/SREs can provide property values to these configs without the need to recompile the actual service**.
- It provides **easier transitions** for configuration changes between the development and siteops environments, and **quicker configuration changes** to any environment.

### App-Def File

#### What is app-def?

The app-def file is the **contract between the product to config 2.0**. It lists out all the configs that need to be defined before the service starts up. Because application definitions are tightly coupled with the service and its specific release version (because each release might have different specific config requirements), it's important that **each service version has its own app-def**.

Configuration 2.0 is done roughly through this process:

- Generate application definition(app-def) from the service. Anything that is not defined in the application definition will not be included in the final compiled configs.
- Compile configs based on the application definition.
- Publish compiled configs.
- Use published configs when launching the service.

The app-def file is **tightly coupled with the service and its specific release version**. Each time a new version of a service is published, there is a new app-def file.

The app-def file is in the following format: `<service_name>-<version_number>-app-def.xml`.

#### How does app-def play from service compilation to service deployment?

##### Top-level overview

Here is a top-level picture of the flow from service's source control to deployment:

![cfg2-overview.png](../assets/cfg2-overview.png)

1. Compilation of the service's source code will produce an app-def file.
2. **This app-def file is used to determine which configs should participate during compilation time**. Also during compilation time, **all configs are resolved based on the host, fabric, and other environment variations**. Configs come from ../config folder, which contains .src and .fabric files.
3. The resulted cfg2 compilation is several .cfg files which gets uploaded to artifactory.
4. During deployment, the deployment system grabs the .cfg file from artifactory.
5. When the service starts up, the compiled configs (from .cfg file) gets injected into the service. During this time, all encrypted values are resolved.

##### .cfg Compiled Config File

*.cfg* is the extension for compiled configs. This is the file read by the deployment system to inject the configs into the service. **All configuration has already been resolved and the fully expanded value is in this file**.

[references](https://iwww.corp.linkedin.com/wiki/cf/display/TOOLS/Application+Definition+for+cfg2)

#### [Generate app-def](https://iwww.corp.linkedin.com/wiki/cf/display/TOOLS/gen-app-def+command)

### Basic Application/Container/Fabric configs


### Constant configs

Constant configs are constants that are applied to all fabrics for all services. You can either add to any existing file under ``<MP_NAME>/config/globals/*.src` or add a new filename.src into the globals directory.

> Because all the files under <MP_NAME>/config/globals/ share the same precedence order, the config properties in each .src file must be mutually exclusive to each other. If there is a collision, the cfg2 compiler will error out until this is fixed.

### Group configs

Group configs are configs **shared by a set of fabrics**, used by the *multi-colo effort*.

Group configs is another layer in which configs specific to a particular colo can go. You can define them at the global fabric level, or at the application-specific level.

- When there are configs that need to be part of the same colo, it make sense **not to duplicate the configs across fabrics in the same colo**.
- At the same time, configs that are specific to a colo should not be applied to all fabrics (for instance, **configs for the ei colo [EI1/EI2] should not see configs from the prod colo**).

### Profile configs

Profiles contain a set of configs **across multiple applications**. They can apply **per application level (across all fabrics)**, or to **a specific fabric or group**.

### Tag configs

Tags allow you to group subsets of configs within a service (or fabric) with a different set of configurations.

This allows you to run a service with the same version with a different set of configs without needing to recompile the configs or the service.

These tagged configuration have a **higher precedence over the non-tagged configs at the same level**.

### Machine/Instance Level Configs

These configurations **follow a specific filename format** (or they'll be mistaken as tag configs)

These configs can only be defined in the application fabric-specific level.

### Pseudo Fabric Configs

Pseudo fabrics have a **higher precedence level with the specific level of configs**. For instance, pseudo global fabric has a higher precedence than the actual global fabric, but has a lower precedence than application level.

These are the areas that to define pseudo fabrics:

| Name                   | Path                             |
|------------------------|----------------------------------|
| Global Fabric level    | fabric/QEI1.fabric               |
| App-Fabric level       | app/<service_name>/QEI/*         |
| Container-Fabric level | container/<container_name>/QEI/* |

### Test Configs

These are configs for your unit/integration tests in your test module.

### Full Picture

```
<MP_NAME>/
  config/ <-- Config directory
    fabric/
      EI1.fabric       \ Global fabric configs shared by all services, but specific to that
      PROD-ELA4.fabric / fabric
      globals/
        ports.src       <-- Constant configs
        env-info.src    <-- Constant configs
      groups/
        ei.src          <-- Group-specific configs shared by a set of fabrics
      profiles/
        a.src           <-- Profile 'a' config, shared by all fabrics
        EI1/
          a.src         <-- Profile 'a' config, used by EI1 fabric
        groups/
          ei/
            a.src       \   Profile 'a' and 'b' configs,
            b.src       /   used by group 'ei'
    app/
      beta-war/
        application.src   <-- Application-specific configs for beta-war

      sample-war/
        application.src   <-- Application-specific configs for sample-war                           
        EI1/
          fabric.src      <-- Fabric-specific configs (EI1) for sample-war
          bar.src         <-- Tagged config 'bar' for sample-war, for EI1 fabric only
        foo.src           <-- Tagged config 'foo' for sample-war
        QEI1/
          fabric.src      <-- Pseudo fabric-specific configs (QEI1) for sample-war
        groups/
          ei.src          <-- Group-specific configs for sample-war
    container/
      sample-container/
        container.src     <-- Container-specific configs
        EI1/
          fabric.src      <-- Fabric-specific configs (EI1)
          machine-ech-fe10.src         <-- machine-level configs
          instance-i001.src            <-- instance-level configs
          instance-ech-fe10-i001.src   <-- machine-instance-level configs

    test/
      sample-test/
        application.src   <-- Application-specific configs                        
        EI1/
          fabric.src      <-- Fabric-specific configs (EI1)

        groups/
          ei.src          <-- Group-specific configs
        profiles          <-- Profile filename, tells which profiles sample-test uses
```

**Application Precedence Order** (highest precedence first):
- app/sample-war/QEI1/fabric.src
- app/simple-war/EI1/instance-ech-fe10-i001.src
- app/simple-war/EI1/machine-ech-fe10.src
- app/simple-war/EI1/instance-i001.src
- app/sample-war/EI1/bar.src
- app/sample-war/EI1/fabric.src
- app/sample-war/groups/qei.src
- app/sample-war/groups/ei.src
- app/sample-war/foo.src
- app/sample-war/application.src
- fabric/QEI1.fabric
- fabric/EI1/frontier.src
- fabric/EI1.fabric
- fabric/profiles/EI1/a.src
- fabric/groups/ei.src
- fabric/profiles/groups/ei/a.src
- fabric/profiles/a.src
-fabric/globals/ports.src & fabric/globals/env-info.src

**Container Precedence Order** (highest precedence first):
- container/sample-container/QEI1/fabric.src
- container/simple-container/EI1/instance-ech-fe10-i001.src
- container/simple-container/EI1/machine-ech-fe10.src
- container/simple-container/EI1/instance-i001.src
- container/sample-container/EI1/fabric.src
- container/sample-container/groups/qei.src
- container/sample-container/groups/ei.src
- container/sample-container/application.src
- fabric/QEI1.fabric
- fabric/EI1.fabric
- fabric/profiles/EI1/a.src
- fabric/groups/ei.src
- fabric/profiles/groups/ei/a.src
- fabric/profiles/a.src
- fabric/globals/ports.src & fabric/globals/env-info.src

### Encrypting Values in Config

```
# riddler -f <fabric_name> --encrypt <string_to_encrypt> --key <key>
riddler -f EI1 --encrypt "myprivatepassword" --key "test_password"

Encrypted-AES/CBC/PKCS5Padding(0asvrUI_-kJmVZRTcg6e6AvaJCMwzy9x-cqkTSFWSCW,2UVTvIa8mPHSdVHlIUfp58,1QsSlQ)
```

### [cfg2 for Play FAQs](https://iwww.corp.linkedin.com/wiki/cf/pages/viewpage.action?pageId=34863474#cfg2FAQ)

#### How are App-Defs generated for *Play* applications?

The App-Def file is an xml file that explicitly lists the properties required by an application for a specific version of that application. **We compile the config src files against this app-def, meaning only properties that exist in the app-def will end up in the compiled config**.

App-defs are generated and uploaded to Artifactory during the build phase of PCL after a commit has been made to the product. For Play apps, the generated app-def is simply an enumeration of the properties listed in the application.src file at the time of the commit.

You can generate an app-def locally by running *mint build*. It will be located at the `build/<payload-name>/<payload-name>-<version>-app-def.xml`. You can inspect this file to verify what properties would end up in your app-def based on your current config set up.

#### I just added a new property to my configs but it is not showing up in my compiled configs. What's happening?

As mentioned earlier, only properties listed in the app-def will end up in the compiled config. **When you add a brand-new property to your application.src file, you must also trigger a build of your product such that a new app-def containing the new property is created.** This is because `the app-def generated during the build process is simply an enumeration of the properties listed in the application.src file`. You can now go ahead and deploy the new version of your product and the compiled config will contain your property.

#### My property is still not showing up. What's happening?

Ensure you have done the following:

- You have committed your property to the application.src file. **You can override it in fabric.src but it must exist in application.src**
- After committing the property, you triggered a build of your product (you can use the **trigger-build** command)
- You deployed the new version (and not an older version that was created before you committed the new property)

#### I modified the value for an existing property. Do I still need to trigger a build?

No, if you are simply modifying a property value, you can commit the config and deploy the config out with a deploy-config. **You only need to trigger a build if you are adding a brand new config property**.


---

## Invocation Context

### What it is?

- A map of data that we carry around with any service invocation
- Manages data related to the current call tree

### Why we need it?

Be able to perform analysis on each rpc call made between services. We need this data to help detect problems, perform capacity planning and headroom analysis, etc.

- Call Tracing: Page Key, Rpc Trace, Service Call Events
- EKG, Cost 2 Serve, Call Tree App
- Request Level Logging
- RTF, QD, Data Center, and DS Master/Slave Routing

### Where it is?

IC data is typically sent via a *multi-valued HTTP header value*.
`X-LI-R2-W-IC-1: urlEncoded<key1>=urlEncoded<value1>,urlEncoded<key2>=urlEncoded<value2>,...`

### IC Example: RpcTrace

- RpcTrace represents the service call stack
- Helps explain where requests are coming from and why
- Included in the `public_access.log` file of each service

### IC Transport

- Transported from service to service along with each service call
- Supported by each service call protocol

![IC-transport.png](../assets/IC-transport.png)

### IC Handling

- Read off each incoming request
- Included as part of each outgoing request
- IC is maintained in a thread local during request processing

![IC-handling.png](../assets/IC-handling.png)

#### Common Errors

##### Dropped IC

- Typically indicates the EC was not handled correctly
- Undecorated thread pool, timer, processor, etc.
- Unique threading pattern

##### Warnings are logged when making service calls without IC data

EKG tickets are created – but not directly assigned

##### IC/trace is repaired, but not fully functional

Trace Context = “No Context Set”

#### Common Warnings

- ICMissingException
- ICAlreadyExistsException
- TraceDataMissingException
- TraceDataAlreadyExistsException


---

## [ELK](https://iwww.corp.linkedin.com/wiki/cf/display/SOP/ELK+Home#ELKHome-WheredoIStart?)

### ELK Stack

![ELK infrastructure](../assets/elk-infrastructure.png)

### Logstash

![logstash pipeline](../assets/logstash-pipeline.png)
