task :env do
  home = ENV['FLEX_HOME']

  if home && File.exist?("#{home}/bin")
    ENV['PATH'] += ":#{home}/bin"
  end

  if(`which mxmlc`.strip.empty?)
    raise "Unable to find mxmlc. Please put your flex sdk on the path, or set FLEX_HOME"
  end
end

task :build => :env do
  sh "mxmlc -compiler.library-path+=vendor/as3corelib.swc uploadify.mxml"
end

task :default => :build 
