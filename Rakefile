task :build do
  sh "rm -rf _site"
  sh "mkdir _site"
  sh "jekyll"
end

task :default do
  sh "jekyll --server 4000 --auto"
end

task :deploy => :build do
  sh "rsync -rtz --delete _site/ root@t0g.de:/var/www/vhosts/pirix.org/"
end