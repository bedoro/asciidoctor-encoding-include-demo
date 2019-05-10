Including files with CP1252
---

Build the project using
```
mvn -e validate
```

or try
```
mvn -e validate -Dfile.encoding=UTF-8
```

The error you should see with both commands:
```
[ERROR] Failed to execute goal org.asciidoctor:asciidoctor-maven-plugin:1.6.0:process-asciidoc (asciidoc-to-html) on project com.bedoro.asciidoctor-build: Execution asciidoc-to-html of goal org.asciidoctor:asciidoctor-maven-plugin:1.6.0:process-asciidoc failed: org.jruby.exceptions.ArgumentError: (ArgumentError) invalid byte sequence in UTF-8 -> [Help 1]
org.apache.maven.lifecycle.LifecycleExecutionException: Failed to execute goal org.asciidoctor:asciidoctor-maven-plugin:1.6.0:process-asciidoc (asciidoc-to-html) on project com.bedoro.asciidoctor-build: Execution asciidoc-to-html of goal org.asciidoctor:asciidoctor-maven-plugin:1.6.0:process-asciidoc failed: org.jruby.exceptions.ArgumentError: (ArgumentError) invalid byte sequence in UTF-8
        at org.apache.maven.lifecycle.internal.MojoExecutor.execute(MojoExecutor.java:212)
        at org.apache.maven.lifecycle.internal.MojoExecutor.execute(MojoExecutor.java:153)
        at org.apache.maven.lifecycle.internal.MojoExecutor.execute(MojoExecutor.java:145)
        at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject(LifecycleModuleBuilder.java:116)
        at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject(LifecycleModuleBuilder.java:80)
        at org.apache.maven.lifecycle.internal.builder.singlethreaded.SingleThreadedBuilder.build(SingleThreadedBuilder.java:51)
        at org.apache.maven.lifecycle.internal.LifecycleStarter.execute(LifecycleStarter.java:128)
        at org.apache.maven.DefaultMaven.doExecute(DefaultMaven.java:307)
        at org.apache.maven.DefaultMaven.doExecute(DefaultMaven.java:193)
        at org.apache.maven.DefaultMaven.execute(DefaultMaven.java:106)
        at org.apache.maven.cli.MavenCli.execute(MavenCli.java:863)
        at org.apache.maven.cli.MavenCli.doMain(MavenCli.java:288)
        at org.apache.maven.cli.MavenCli.main(MavenCli.java:199)
        at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
        at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
        at java.lang.reflect.Method.invoke(Method.java:498)
        at org.codehaus.plexus.classworlds.launcher.Launcher.launchEnhanced(Launcher.java:289)
        at org.codehaus.plexus.classworlds.launcher.Launcher.launch(Launcher.java:229)
        at org.codehaus.plexus.classworlds.launcher.Launcher.mainWithExitCode(Launcher.java:415)
        at org.codehaus.plexus.classworlds.launcher.Launcher.main(Launcher.java:356)
Caused by: org.apache.maven.plugin.PluginExecutionException: Execution asciidoc-to-html of goal org.asciidoctor:asciidoctor-maven-plugin:1.6.0:process-asciidoc failed: org.jruby.exceptions.ArgumentError: (ArgumentError) invalid byte sequence in UTF-8
        at org.apache.maven.plugin.DefaultBuildPluginManager.executeMojo(DefaultBuildPluginManager.java:145)
        at org.apache.maven.lifecycle.internal.MojoExecutor.execute(MojoExecutor.java:207)
        ... 20 more
Caused by: org.asciidoctor.internal.AsciidoctorCoreException: org.jruby.exceptions.ArgumentError: (ArgumentError) invalid byte sequence in UTF-8
        at org.asciidoctor.internal.JRubyAsciidoctor.convertFile(JRubyAsciidoctor.java:498)
        at org.asciidoctor.internal.JRubyAsciidoctor.convertFile(JRubyAsciidoctor.java:469)
        at org.asciidoctor.maven.AsciidoctorMojo.renderFile(AsciidoctorMojo.java:469)
        at org.asciidoctor.maven.AsciidoctorMojo.execute(AsciidoctorMojo.java:253)
        at org.apache.maven.plugin.DefaultBuildPluginManager.executeMojo(DefaultBuildPluginManager.java:134)
        ... 21 more
Caused by: org.jruby.exceptions.ArgumentError: (ArgumentError) invalid byte sequence in UTF-8
        at org.jruby.RubyString.split(org/jruby/RubyString.java:4057)
        at RUBY.apply_subs(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/substitutors.rb:130)
        at RUBY.content(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/block.rb:116)
        at RUBY.listing(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/converter/html5.rb:632)
        at RUBY.convert(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/converter/base.rb:38)
        at RUBY.convert(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/abstract_block.rb:75)
        at RUBY.content(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/abstract_block.rb:84)
        at org.jruby.RubyArray.map(org/jruby/RubyArray.java:2577)
        at RUBY.content(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/abstract_block.rb:84)
        at RUBY.section(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/converter/html5.rb:369)
        at RUBY.convert(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/converter/base.rb:38)
        at RUBY.convert(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/abstract_block.rb:75)
        at RUBY.content(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/abstract_block.rb:84)
        at org.jruby.RubyArray.map(org/jruby/RubyArray.java:2577)
        at RUBY.content(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/abstract_block.rb:84)
        at RUBY.section(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/converter/html5.rb:368)
        at RUBY.convert(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/converter/base.rb:38)
        at RUBY.convert(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/abstract_block.rb:75)
        at RUBY.content(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/abstract_block.rb:84)
        at org.jruby.RubyArray.map(org/jruby/RubyArray.java:2577)
        at RUBY.content(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/abstract_block.rb:84)
        at RUBY.content(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/document.rb:1261)
        at RUBY.document(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/converter/html5.rb:177)
        at RUBY.convert(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/converter/base.rb:38)
        at RUBY.convert(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor/document.rb:1190)
        at RUBY.convert(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor.rb:1521)
        at RUBY.convert_file(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor.rb:1595)
        at org.jruby.RubyIO.open(org/jruby/RubyIO.java:1157)
        at RUBY.convert_file(uri:classloader:/gems/asciidoctor-1.5.8/lib/asciidoctor.rb:1595)
```
