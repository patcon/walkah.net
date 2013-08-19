task :default => :server
 
desc 'Build site with Jekyll'
task :build do
  jekyll 'build'
end
 
desc 'Build and start server with --auto'
task :server do
  jekyll 'serve -w'
end

desc 'Build and deploy'
task :deploy => :build do
  sh 'rsync -rtzh --delete _site/ walkah.net:/var/www/walkah.net/'
end

def jekyll(opts = '')
  sh 'rm -rf _site'
  sh 'jekyll ' + opts
end
