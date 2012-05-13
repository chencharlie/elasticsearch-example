require 'fileutils'
task :compile do 
  source = FileList['**/*.java']
  sh "javac #{source.collect {|s| "'#{s}'" }.join(' ')}  -classpath ../lib/elasticsearch-*.jar"
end

task :clean do
  FileUtils::Verbose.rm Dir.glob("**/*.class")
end

task :package do
  objects = FileList['**/*.class']
  sh "jar cf MyNativeScript.jar #{objects.collect {|s| "'#{s}'" }.join(' ')}"
end

task :build => [:clean, :compile, :package]
