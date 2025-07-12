CREATE & LAUNCH EC2 INSTANCE. INSTALL NGINX SERVER ON IT.

1. Launched new AWS EC2 instance with Ubuntu Image
2. During EC2 instance configuration downloaded .pem file / keypair file , which contains secret key and it helps to connect to EC2 instance via GitBash.
3. Allowed SSH and HTTP inbound rules during EC2 instance configuration. SSH Port : 22 & HTTP Port : 80 -- Security Type : Anywhere.
4. Launch Instance and copy public IPv4 IP
5. Open GitBash from your local machine type following cmnds . Before that move "key pair" file to your project directory.
    cd "Paste path where your Project file are saved"
    chmod 400 <Your Key pair File Name.pem>  -- Helps to change file permission. Only Owner of the file can read it. Rest of the people cant have any permission
    ssh -i <Your Key Pair file name.pem> ubuntu@<ec2 instance public IP>  -- Way to connect to EC2 instance via GitBash. If you launched with Linux image then use ec2-user instead of ubunutu.
6. Install Web Server on EC2 instance by running below cmnds.
    sudo apt update
    sudo apt install nginx -y
    sudo systemctl start nginx
    sudo systemctl enable nginx
7. type following text to check whether it is really installed and server is working or not.
    echo "<h1> Installed and running nginx server </h1>" | sudo tee /var/www/html/index.html
8. On Browser type "http://<your EC2 instance Public IP>" . Written text will display.
-------------------------------------------------------------------------------------------------------------------------------------------------

CREATE WEB FILE IN LOCAL

9. Create simpe Webapp file and save it as index.html
10. Create README.md file