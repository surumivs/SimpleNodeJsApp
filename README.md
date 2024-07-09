DEPLOYING A NODE JS APPLICATION ON AWS EC2
****
1.	Create a public repository in your GitHub “SimpleNodeJsApp”
2.	Launch an Ubuntu Ec2 instance and add rules HTTP (port 80) and SSH (port 22)
3.	Connect to Your EC2 Instance
ssh -i /path/to/your-key-pair.pem ubuntu@your-ec2-public-dns
4.	Clone created repo in ec2 instance:
git clone https://github.com/surumivs/SimpleNodeJsApp.git
![image](https://github.com/surumivs/SimpleNodeJsApp/assets/170710844/a893f8ac-f42c-4d96-ba8e-b1e60050892a)
 

5.	Install Node.js
•	sudo apt update
•	sudo apt install nodejs npm -y
Verify the installation
•	node -v
•	npm -v
![image](https://github.com/surumivs/SimpleNodeJsApp/assets/170710844/e03b5d7b-096a-49fa-b2e5-1021d21482a0)
 

6.	Move to our App repo directory and Initialize a New Node.js Project
•	cd SimpleNodeJsApp/
•	npm init -y
 ![image](https://github.com/surumivs/SimpleNodeJsApp/assets/170710844/b324c5b5-0064-4eb7-9cc0-faf73508e914)

 ![image](https://github.com/surumivs/SimpleNodeJsApp/assets/170710844/891c14c1-c752-4b47-863e-77ffaee53adb)


7.	Create the Application File “app.js”
•	vi app.js

const http = require('http');

const hostname = '0.0.0.0';
const port = 3000;

const server = http.createServer((req, res) => {
            res.statusCode = 200;
            res.setHeader('Content-Type', 'text/plain');
            res.end('Hello Surumi, You have successfully completed first simple Nodejs App!\n');
});

server.listen(port, hostname, () => {
            console.log(`Server running at http://${hostname}:${port}/`);
});
 
![image](https://github.com/surumivs/SimpleNodeJsApp/assets/170710844/9f677657-c705-424d-8f0c-e5560fa68bb1)

8.	Run Your NodeJS Application by starting and access through the browser:
•	node app.js
 ![image](https://github.com/surumivs/SimpleNodeJsApp/assets/170710844/b05ecdfd-50bf-4b2a-8dae-d230ee0f4d8b)

•	Add security group inbound rule with 3000 open your browser and navigate to http://your-ec2-public-dns:3000

 ![image](https://github.com/surumivs/SimpleNodeJsApp/assets/170710844/b4cd36ba-0bed-4ac3-a306-b7c5d13fcd98)

