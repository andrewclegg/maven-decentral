# maven-decentral

Snapshots are in the [snapshots branch](https://github.com/andrewclegg/maven-decentral/tree/snapshots), releases are in the [releases branch](https://github.com/andrewclegg/maven-decentral/tree/releases).

## Using maven-decentral in your project

Add the [wagon-git](http://synergian.github.io/wagon-git/troubleshooting.html) repo as a plugin repository:

```xml
<pluginRepositories>
  <!-- ... -->
  <pluginRepository>
    <id>synergian-repo</id>
    <url>https://raw.github.com/synergian/wagon-git/releases</url>
  </pluginRepository>
  <!-- ... -->
</pluginRepositories>
```

Then add the following to your project's pom.xml, in the &lt;repositories&gt; section:

```xml
<repositories>
  <!-- ... -->
  <repository>
    <id>maven-decentral-releases</id>
    <name>Maven Decentral - Andrew Clegg's Maven Releases</name>
    <releases>
      <enabled>true</enabled>
    </releases>
    <snapshots>
      <enabled>false</enabled>
    </snapshots>
    <url>git:releases://git@github.com:andrewclegg/maven-decentral.git</url>
  </repository>
  <!-- ... -->
</repositories>
```

To enable snapshot downloads, add the following too:

```xml
<repositories>
  <!-- ... -->
  <repository>
    <id>maven-decentral-snapshots</id>
    <name>Maven Decentral - Andrew Clegg's Maven Snapshots</name>
    <releases>
      <enabled>false</enabled>
    </releases>
    <snapshots>
      <enabled>true</enabled>
    </snapshots>
    <url>git:snapshots://git@github.com:andrewclegg/maven-decentral.git</url>
  </repository>
  <!-- ... -->
</repositories>
```

## TODO

Fork wagon-git and host it here, so we're completely self-sufficient.

