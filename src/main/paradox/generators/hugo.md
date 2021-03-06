# Hugo

The sbt-site plugin has support for building [Hugo] projects. To enable Hugo site generation, simply enable the associated plugin in your `build.sbt` file:

@@ snip[enablePlugin](../../../sbt-test/hugo/can-use-hugo/build.sbt) { #enablePlugin }

The `hugo` binary must be installed on your `$PATH` in order to be accessible to sbt-site. In addition, this plugin assumes you have a Hugo project under the `src/hugo` directory. To change this, set the `sourceDirectory` key in the `Hugo` scope:

```sbt
sourceDirectory in Hugo := sourceDirectory.value / "doc"
```

You may also change the [base-url](https://gohugo.io/overview/configuration/) that gets passed to the `hugo` command by adjusting the following setting:

@@ snip[baseURL](../../../sbt-test/hugo/can-use-hugo/build.sbt) { #baseURL }

To export environment variables when forking the `hugo` process, for example to render with Hugo's [getenv function](https://hugodocs.info/functions/getenv/), use:

@@ snip[extraEnv](../../../sbt-test/hugo/can-use-hugo/build.sbt) { #extraEnv }

[Hugo]: http://gohugo.io/
