task :default do
  unless File::exists?("build")
    mkdir "build"
  end
  sh "slidedown i18n.md > build/i18n.html"
  puts "Presentation generated successfully"
  sh "open build/i18n.html"
end

task :clean do
  remove_dir "build", :force => true
end