require 'fileutils'

desc "deploy bundles"
task :deploy do
  File.exists?("#{ENV['HOME']}/.vim/bundle") &&
    abort("\n*******\nLooks like we are already deployed.\nrm ~/.vim/bundle to redeploy\n*******")

  FileUtils.ln_s File.dirname(__FILE__), "#{ENV['HOME']}/.vim/bundle"
end

desc "update submodules"
task :update do
  %x(git submodule init)
  %x(git submodule update)
end

desc "pull scripts"
task :pull do
  scripts = File.read(".gitmodules").scan(/path = (.*)/)
  scripts.each do |script|
    puts "Updating #{script}"
    #run "cd #{script}; git reset --hard HEAD ; git pull --rebase ; cd .."
    cd script.first
    cd '..'
  end
end
