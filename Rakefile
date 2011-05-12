require 'fileutils'

desc "deploy bundles"
task :deploy do
  File.exists?("#{ENV['HOME']}/.vim/bundle") &&
    abort("\n*******\nLooks like we are already deployed.\nrm ~/.vim/bundle to redeploy\n*******")

  FileUtils.ln_s File.dirname(__FILE__), "#{ENV['HOME']}/.vim/bundle"
end

desc "update submodules"
task :update do
  sh "git submodule init"
  sh "git submodule update"
end

desc "pull scripts"
task :pull do
  sh "git submodule foreach git pull --rebase"
  sh "git submodule foreach git submodule init"
  sh "git submodule foreach git submodule update"
end
