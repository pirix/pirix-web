task :build do
  sh "rm -rf _site"
  sh "mkdir _site"
  sh "jekyll build"
end

task :default do
  sh "mkdir -p _site"
  sh "jekyll serve"
end

task :deploy => :build do
  sh "rsync -rtz --delete _site/ root@t0g.de:/var/www/vhosts/pirix.org/"
end