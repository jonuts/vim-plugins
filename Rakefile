require 'fileutils'

desc "deploy bundles"
task :deploy do
  File.exists?("#{ENV['HOME']}/.vim/bundle") &&
    abort("\n*******\nLooks like we are already deployed.\nrm ~/.vim/bundle to redeploy\n*******")

  FileUtils.ln_s File.dirname(__FILE__), "#{ENV['HOME']}/.vim/bundle"
end
