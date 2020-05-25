# gwt-http
![GWT3/J2CL compatible](https://img.shields.io/badge/GWT3/J2CL-compatible-brightgreen.svg)

A future-proof port of the `com.google.gwt.http.HTTP` GWT module,
with no dependency on `gwt-user` (besides the Java Runtime Emulation),
to prepare for GWT 3 / J2Cl.

##  Browser compatibility

The code should be compatible with all evergreen browsers,
and Internet Explorer 10 and 11.

### Dependency

```xml
<dependency>
    <groupId>org.gwtproject.http</groupId>
    <artifactId>gwt-http</artifactId>
    <version>1.0-SNAPSHOT</version>
</dependency>
```

##  Migrating from `c.g.g.http.HTTP`

1. Add the dependency to your build.

   For Maven:

   ```xml
   <dependency>
     <groupId>org.gwtproject.http</groupId>
     <artifactId>gwt-http</artifactId>
     <version>${gwtHttpVersion}</version>
   </dependency>
   ```

   For Gradle:

   ```gradle
   compile "org.gwtproject.http:gwt-http:${gwtHttpVersion}"
   ```

2. Update your GWT module to use

   ```xml
   <inherits name="org.gwtproject.http.HTTP" />
   ```

   (either change from `com.google.gwt.http.HTTP`,
   or add it if you inherited it transitively from another GWT module)

3. Change your `import`s in your Java source files:

   ```java
   import org.gwtproject.http.client.RequestBuilder;
   import org.gwtproject.http.client.URL;
   import org.gwtproject.http.client.UrlBuilder;
   ```


### Instructions
To build gwt-http:

* run `mvn clean install`

on the parent directory.

To run the j2cl tests:

* switch to the 'gwt-http-j2cl-tests' directory
* run `mvn j2cl:clean` & `mvn j2cl:test`

