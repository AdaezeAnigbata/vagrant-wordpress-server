Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.network "private_network", ip: "192.168.56.30"

  config.vm.provision "shell", inline: <<-SHELL
    # Update and install Nginx
    apt-get update
    apt-get install -y nginx

    # Create a styled HTML page using cat <<EOF
    cat <<EOF > /var/www/html/index.html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Adaeze's Nginx Assignment</title>
    </head>
    <body>
            <h1>Hello! 👋</h1>
            <h2>My name is Adaeze Anigbata</h2>
            <p>I am a student of the she code scholarship program - cohort 3.</p>
            <p> I am learning DevOps Engineering </p>
            <p>This simple HTML page is being served by an automated <strong>Nginx</strong> web server.</p>
    </body>
    </html>
EOF

    # Restart Nginx to serve the new page
    systemctl restart nginx
  SHELL
end