task :sass do
  cd "stylesheets/sass"
  Dir["*.sass"].each do |e|
    sass = e.clone
    e["sass"] = "css"
    unless File::exists?("../compiled")
      mkdir "../compiled"
    end
    
    sh "sass #{sass} > ../compiled/#{e}"
  end
  cd "../.."
end

task :default => :sass do
  unless File::exists?("build")
    mkdir "build"
  end
  sh "slidedown src/i18n.md -t #{pwd}/views/import > build/i18n.html"
  puts "Presentation generated successfully"
  sh "open build/i18n.html"
end

task :clean do
  remove_dir "build", :force => true
end
