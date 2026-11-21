# Minestom Console

JLine integration for Minestom with syntax highlighting and auto-completion

## Installation

::: code-group

```kts [Gradle (Kotlin)]
repositories {
    maven("https://maven.skylite.gg/releases")
}

dependencies {
    implementation("gg.skylite:console:2026.11.15-26.3")
}
```

```groovy [Gradle (Groovy)]
repositories {
    maven {
        url 'https://maven.skylite.gg/releases'
    }
}

dependencies {
    implementation 'gg.skylite:console:2026.11.15-26.3'
}
```

```xml [Maven]
<repositories>
    <repository>
        <id>skylite</id>
        <url>https://maven.skylite.gg/releases</url>
    </repository>
</repositories>

<dependencies>
    <dependency>
        <groupId>gg.skylite</groupId>
        <artifactId>console</artifactId>
        <version>2026.11.15-26.3</version>
    </dependency>
</dependencies>
```

:::

## Usage

::: code-group

```java [Java]
import gg.skylite.console.Console;
import net.minestom.server.MinecraftServer;

import java.io.IOException;

void main() throws IOException {
    var server = MinecraftServer.init();

    var console = Console.builder().build();
    console.start();
    Runtime.getRuntime().addShutdownHook(new Thread(console::close));

    server.start("0.0.0.0", 25565);
}
```

```kotlin [Kotlin]
import gg.skylite.console.Console
import net.minestom.server.MinecraftServer

fun main() {
    val server = MinecraftServer.init()

    val console = Console.builder().build()
    console.start()
    Runtime.getRuntime().addShutdownHook(Thread(console::close))

    server.start("0.0.0.0", 25565)
}
```

:::
