###############################################################################
# Configuration
###############################################################################
BASE_DIR = File.expand_path(File.dirname(__FILE__))


###############################################################################
# Nginx Tasks
###############################################################################
namespace :nginx do

  desc "Installs nginx if necessary."
  task :install do
    nginx_path = `which nginx`
    if nginx_path.nil? || nginx_path.empty?
      system("sudo port install nginx +ssl")
    end
    if !File.exist?("#{BASE_DIR}/pem/nginx.pem")
      Dir.chdir("#{BASE_DIR}/pem") do
        system("./makepem")
      end
    end
  end

  desc "Starts nginx."
  task :start do
    system("sudo nginx -c #{BASE_DIR}/conf/nginx.conf -p #{BASE_DIR}/")
  end

  desc "Stops nginx."
  task :stop do
    system("sudo nginx -c #{BASE_DIR}/conf/nginx.conf -p #{BASE_DIR}/ -s quit")
  end
end
