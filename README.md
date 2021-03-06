# Collection Example plugin for Springfox
[![Build Status](https://travis-ci.org/aaitmouloud/springfox-collection-example-plugin.svg?branch=master)](https://travis-ci.org/aaitmouloud/springfox-collection-example-plugin)

## What does it do
It allows you to have a correct example generated for all `java.util.Collection` typed properties.

For example, this:
```java
@ApiModelProperty(value ="my property description", example = "2019-12-20T12:00:00")
@NotNull
private List<LocalDateTime> dates;
```

Would generate this:
```json
{
    "properties": {
        "autresDates": {
            "type": "array",
            "example": [
                "2019-12-20T12:00:00"
            ],
            "description": "my property description",
            "items": {
                "type": "string",
                "format": "date-time"
            }
        }
    }
}
```

## Usage
### Maven
Add this to your `pom.xml` in the `<dependencies>`

```xml
<dependency>
    <groupId>com.github.aaitmouloud</groupId>
    <artifactId>springfox-collection-example-plugin</artifactId>
    <version>2.9.2</version>
</dependency>
```

### Gradle
Add this to your `dependencies` in your `build.gradle`

```groovy
implementation 'com.github.aaitmouloud:springfox-collection-example-plugin:2.9.2'
```
### Spring
Just add the `springfox.collection.example.plugins` package to your Spring context

For example, while using Spring Boot: 
```java
@ComponentScan({"springfox.collection.example.plugins"})
public class MyConfigurationClass {
}
``` 


## See also
* https://github.com/springfox/springfox
* http://springfox.io
