# Apache Ivy Shell wrapper

[Apache Ivy](http://ant.apache.org/ivy/) is an artifact and dependency manager. If you didn't know anything about Apache Ivy, this wrapper won't help you at all! But feel free to learn about Apache Ivy because it's a great tool improving your software integration flow.

The common way to use Apache Ivy is [Ant](http://ant.apache.org/) or [Gradle](http://www.gradle.org/), it can also be used in command line as explained by the [official documentation](http://ant.apache.org/ivy/history/latest-milestone/standalone.html).

Usually, you invoke it directly through Java:

```bash
java -jar ivy.jar -?
```

A little bit verbose, isn't it?! When you want to use Ivy in command line all the day, it might be a pain. This is where this wrapper comes. Simply put it in your `PATH` and invoke it with the Apache Ivy command line arguments as any other command.

## Installation

```bash
$ git clone https://github.com/opatry/ivy-wrapper.git
$ export PATH=ivy-wrapper/ivy:${PATH}
$ export IVY_HOME=path/to/your/ivy/installation
$ ivy -version
```

If you have `~/bin` in your `PATH` (or something like that), you could link the repository version of the ivy wrapper in it (considering you are in the `ivy-wrapper` repository source tree):

```bash
$ ln -s `pwd`/ivy ~/bin/ivy
```

You may have noticed the `IVY_HOME` export above, define it to the path where your Apache Ivy installation resides, if you do not, the script will check it and exit with an error message.

## Usage

Considering you have the installation steps done in a permanent way, you may use the Apache Ivy command line as usual.

The following command will download [JUnit](http://junit.org/) from the [Maven](http://maven.apache.org/) [central repository](http://mvnrepository.com/) or your ivy cache if already downloaded.

```bash
$ ivy -dependency junit junit latest.release
```

Which is an equivalent of the `ivy.xml` dependency expression:

```xml
<dependency org="junit" name="junit" rev="latest.release"/>
```

For further details on ivy and its command line usage, please refer to the official documentation.
