Dispatch Reboot
---------------

[![Build Status](https://travis-ci.org/dispatch/reboot.svg?branch=master)](https://travis-ci.org/dispatch/reboot)

Dispatch reboot is a rewrite of the Dispatch library for HTTP interaction in Scala, using
[async-http-client][async], commonly called AHC, as its underlying transport. For more info, see the
[Dispatch documentation site][docs].

Dispatch requires that you use Java 8 as AHC requires it.

[docs]: https://dispatch.github.io/reboot/Dispatch.html
[async]: https://github.com/AsyncHttpClient/async-http-client

## Getting Dispatch

Stable releases of Dispatch are published to Maven Central. As such, you can pull in the current
stable release by simply adding a library dependency to your project for the correct version.

To get the latest stable release, 0.14.0, simply add the following to your `build.sbt`:

```scala
libraryDependencies += "org.dispatchhttp" %% "dispatch-core" % "0.14.0"
```

If Gradle is more your style, you could also use this style:

```scala
compile "org.dispatchhttp:dispatch-core_2.12:0.14.0"
```

### Snapshot releases

We're also currently publishing snapshot releases for 0.14.x-SNAPSHOT to Sonatype snapshots.
If you'd like to test your code with AHC 2.1 before it's final, taking one of these snapshots
out for a spin is the way to do it.

The following instructions will get you your snapshot:

```scala
resolvers +=
  "Sonatype OSS Snapshots" at "https://oss.sonatype.org/content/repositories/snapshots"

libraryDependencies += "org.dispatchhttp" %% "dispatch-core" % "0.14.0-SNAPSHOT"
```

## Versioning and Support

Dispatch version numbers loosely follow SemVer. The version number format is:

```
[major].[minor].[patch]
```

A distinct (major, minor) combination is called a "release series" or "series" for our purposes.

Two stable series of Dispatch are supported at a time, with one series prior to that receiving
"Critical" security updates in Dispatch itself or critical security fixes in AHC that have broken
binary compatibility. All earlier versions of Dispatch are officially unsupported and will not
receive any fixes or changes.

The following chart outlines what versions of Dispatch support what versions of AHC and Scala and
their current support status:

|Version           | AHC Version  |Scala Versions |Support       |Branch
|------------------|--------------|---------------|--------------|---------------------------------|
|0.10.0            |1.7.11        |2.9.3,2.10     |None          |                                 |
|0.11.2            |1.8.10        |2.9.3,2.10,2.11|None          |                                 |
|0.11.4            |1.9.40        |2.10,2.11      |None          |                                 |
|0.12.3            |1.9.40        |2.11,2.12      |Critical only |0.12.x                           |
|0.13.3            |2.0.38        |2.11,2.12      |Full support  |0.13.x                           |
|0.14.0            |2.1.2         |2.11,2.12      |Full support  |0.14.x                           |
|1.0.0-M1          |2.4.9         |2.11,2.12      |Development   |master                           |

Because the AsyncHttpClient does not adhere to semantic versioning, and its versions can increment
quite quickly at times, beginning with 0.14 Dispatch will only use the latest (major, minor) AHC
version that's available at the time its being developed. You may not be able to find a Dispatch
version for every version of AHC if AHC went through a quick release clip.

## Getting Help and Contributing

Please see our [Contributing Guide][contributing] for information on how to contribute and get help
with Dispatch.

[contributing]: https://github.com/dispatch/reboot/blob/master/CONTRIBUTING.md
